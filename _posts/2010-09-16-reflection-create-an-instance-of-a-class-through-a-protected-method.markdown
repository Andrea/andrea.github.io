---
author: roundcrisis
date: 2010-09-16 20:01:04+00:00
layout: single
classes: wide
slug: reflection-create-an-instance-of-a-class-through-a-protected-method
title: Reflection - Create an instance of a class through a protected method
wordpress_id: 674
categories:
- net
tags:
- reflection
---

I had a bit of trouble getting to this, so for self reference more than anything, I thought I d post about it.

Given the following class

    {% highlight c# %}
    	
        public class MyClass	
       {		
               private string _name;
    
               public string Name { get { return this._name;}}
    
               protected MyClass(string name)
              {
                   _name = name;		
              }
      }    
{% endhighlight %}

I thought that the following would be the way to create an instance of it:

    
    {% highlight c# %}
    Activator.CreateInstance(typeof(MyClass), BindingFlags.NonPublic, null, new object[] { "MyName" }, CultureInfo.CurrentCulture);
    {% endhighlight %}    

    However it throws a MissingMethodException: Constructor on type 'ReflectionCreateInstance.MyClass' not found. However if we add the Binding Flag for instance then it works.

    {% highlight c# %}
    	
    [Fact]
    public void When_creating_with_activator_Must_use_apropriate_binding_flags()
    {
    	string myname = "MyName";
    
    	var myClass = (MyClass)Activator.CreateInstance(
    					typeof(MyClass), 
    					BindingFlags.Instance| BindingFlags.NonPublic, 
    					null, 
    					new object[] { myname }, 
    					CultureInfo.CurrentCulture);
    
    	Assert.Equal(myname, myClass.Name);
    }	
    {% endhighlight %}



    
    If you try this with <b>type.GetConstructor</b> or <b>type.GetConstructors </b>the result is the same. 

    
    Checking the <a href="http://msdn.microsoft.com/en-us/library/system.reflection.bindingflags.aspx" target="_blank">documentation for BindingFlag</a>.Instance I find </span>

    
    <a href="http://roundcrisis.files.wordpress.com/2010/09/capture.png"><img src="http://roundcrisis.files.wordpress.com/2010/09/capture_thumb.png" style="display:inline;border-width:0;" title="Capture" height="370" width="674" alt="Capture" border="0"></img></a>

    So it was a case of RTFM I guess :D
