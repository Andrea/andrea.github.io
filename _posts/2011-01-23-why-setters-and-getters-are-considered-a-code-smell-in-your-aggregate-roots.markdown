---
author: roundcrisis
comments: true
date: 2011-01-23 19:38:11+00:00
layout: single
classes: wide
slug: why-setters-and-getters-are-considered-a-code-smell-in-your-aggregate-roots
title: Why Setters and Getters are considered a code smell in your Aggregate Roots
wordpress_id: 768
categories:
- cqrs
- ddd
tags:
- aggregate
- ddd
- setters
---

Say we are not concerned with the query side of things (because we have an autonomous query service that need not know about your aggregate roots). With that in mind, in which cases do we **need** to know about the aggregate root private data?

 

I can think of one case - when checking for duplication. Then we would have to 

 

       
    * Be happy with eventual consistency (ie some check before actually trying to save) or 
     
    * rely on the persistence layer for uniqueness and on failure, get a meaningful error. 
    

In any other situation, we are likely to be doing something that is meaningful to your domain. For example, lets pretend a product stock amount had to change, the code would look like this

 
    
    
    [sourcecode language="csharp" padlinenumbers="true"]
    Product product = _repository.Get(id);
    product.Stock = 2;
    _repository.Save(product);
    
    class Product
    {
         public int Stock {get; set;}
    }
    [/sourcecode]
    








That code would have probably lived in a service, or even worse, in a controller What are the problems with this?






  
  * Lack of intent. When you look at the code for Product, you’ ll see a Stock (or quantity) property, and in this case its a pretty simple field. However you have no idea from looking at the code, how this property is used. 


  
  * Possible implicit behaviour. There is always a chance that the setter contains some logic . 


  
  * Context, perhaps adding Stock has certain rules, maybe when >100 are received then someone has to be notified, or they need to be moved to another warehouse. 





Instead, you can write an AddStock method, which in reality would do something a bit more explicit ( I'm sure you could call it StockDelivered or similar, but I guess it depends on your domain …)






    
    
    [sourcecode language="csharp" autolinks="false"]
    Product product = _repository.Get(id);
    product.AddStock(45);
    _repository.Save(product);
    
    
    // and in the product AR
    class Product
    {
           public void AddStock(int receivedStock)
    		{
    			Contract.Requires<ArgumentException>(receivedStock>= 0);
    		   	_stock += receivedStock;
    		}
    }
    [/sourcecode]
    










This is a more explicit design. However, the question of testability comes to mind, and the way you write your tests depends on the flavour of DDD you are using. If you are using DDD with CQRS/ES, then you would be publishing an event with the changes. If you are not, then you could rely on checking the product stock before and after the operation, through a query service. 









**Related Articles**





[The Flawed theory behind unit testing](http://michaelfeathers.typepad.com/michael_feathers_blog/2008/06/the-flawed-theo.html) (Feathers)





[Doing it wrong: getters and setters](http://typicalprogrammer.com/?p=23)
