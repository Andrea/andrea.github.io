---
author: roundcrisis
comments: true
date: 2011-01-03 13:20:19+00:00
layout: single
classes: wide
slug: what-is-cqrs-and-other-related-terms-modelling-and-testing-part-3
title: What is CQRS and other related terms - Modelling and testing - Part 3
wordpress_id: 761
categories:
- .net
- bdd
- cqrs
- ddd
tags:
- cqrs/es
- ddd
- modelling
- software architecture
---

This post belongs to a series of posts on CQRS/ES

[Part 1 – introductory terms and overview](http://roundcrisis.com/2010/11/17/what-is-command-query-responsibility-segregation-cqrs-and-other-related-terms-part-1/)

[Part 2 – Event sourcing and information about commands](http://roundcrisis.com/2010/11/30/what-is-cqrs-and-other-related-terms-part-2-2/)

So, we are moving on.

I thought I’d put these two topics close, it seems to me  that they are related, I ve been using BDD to test this

[![DDDDevision_big](http://roundcrisis.files.wordpress.com/2011/01/ddddevision_big_thumb.jpg)](http://roundcrisis.files.wordpress.com/2011/01/ddddevision_big.jpg)

After all, what I'm testing is much more than a unit, and I'm interested in the whole loop. What I find interesting here is that since we are talking about actions when we talk about commands and we are also talking about past events, the **Given**, **When**, **Then **become very rather obvious.

So, you can say something like:


```
Given a NewCustomerCommand with "Name"
 and a NewCustomerCommandHandler
When I Execute the Command
Then a CustomerCreatedEvent is published
 and Customer with "Name" exists
```


and, if you, like me, are using StoryQ, this story can look like


```

                .WithScenario("Create new customer")
                    .Given(ANewCustomerCommandWith_, "Name")
                        .And(ANewCustomerCommandHandler)
                    .When(IExecuteTheCommand)
                    .Then(ACustomerCreatedEventIsPublished)
                        .And(CustomerWithName_Exists, "Name")
```




With this in mind, its not hard to imagine the code to make this happen, and because of that, the focus remains on the modelling, when I see this code, I can’t help but think, Do I really need to create a new customer to be able to process orders? Is the name all that relevant?, maybe the email is more representative… all of these are domain questions, this is exactly the kind of questions that should arise, this focus is on the domain is one of the most interesting advantages of CQRS. And we need to change our code. Your testing points are at the command level, at the query level and/or at the event level.

An interesting advantage of testing in a BDD style is that you have very concise, **runnable** documentation, and can kick the conversation off, with your domain expert. Here you could say, wait a minute, my domain expert doesn’t know about commands, or queries. Well then perhaps you need to move the layer of testing up a bit higher to the UI.  Testing points go a layer above, another option is test at both levels.


## Summary





	
  * Behaviour Driven tests help you model the domain

	
  * Your testing points are your commands, command Handler, query services and events. No need to mess around with aggregate roots directly, and hence why no need for getters on the aggregate roots

	
  * Your tests are executable documentation


UPDATE: Next up Validation
