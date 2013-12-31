---
author: roundcrisis
comments: true
date: 2010-11-17 22:19:37+00:00
layout: post
slug: what-is-command-query-responsibility-segregation-cqrs-and-other-related-terms-part-1
title: What is Command Query Responsibility Segregation (CQRS ) and other related
  terms - part 1
wordpress_id: 723
categories:
- cqrs
- ddd
tags:
- cqrs
- ddd
---

I m preparing for a talk on CQRS and I though I’d support it with a series of posts on the subject. I’d love to get some feedback on this and all the following blog posts. (where I ll be possibly correcting stuff i say here, I can’t promise)

So, I decided to start at the beginning: definitions. When I started to learn about CQRS I just looked at a good few videos, read a bunch of blog posts and then dived into every code example I could find, and then I m working on a system that uses these principles. However, I wanted to roll back and see if I can somewhat formalise what I’ve learned so far. Starting with definitions


## What is CQRS?


Based on [this blog post](http://codebetter.com/blogs/gregyoung/archive/2010/02/16/cqrs-task-based-uis-event-sourcing-agh.aspx) and [others](http://codebetter.com/blogs/gregyoung/archive/2009/08/13/command-query-separation.aspx) , the consensus is something like: CQRS is a pattern that describes the separation of command messages , they change state, from query messages that read state.

Please note this is a pattern (i.e. not an architecture) . if you look around online you ll find that some people seem to see CQRS as a software architecture, it makes sense that this is confusing, I wonder if the “term” evolved so much that it lost its meaning, what most people refer to as CQRS is actually a combination of a good bunch of patterns that work well together.

CQRS is normally used with other patterns such as event sourcing, messaging patterns, task based uis, etc. I’d like to make an emphasis on the guideline bit, for me this is a powerful word, it tells me, something like, paint it some shade of yellow, but I have the choice to use the yellow that makes the room the way I need it to be.

[![](http://farm4.static.flickr.com/3068/3072942016_48ed5f0cac.jpg)](http://domaindrivendesign.org/books3#DDD)Before I started looking at CQRS I was unclear about the relationship between an Aggregate root and the services that serviced it or worked on it. Once I started looking at samples of applications based on CQRS with ES, which was about the time we finished reading the DDD Blue DDD Bible, then it all became clear.  I think the main thing was that the boundaries of the aggregates and the boundaries of each domain were more tangible and made more sense.

Also if using CQRS, you ll find that your aggregate roots change shape, i.e. there are no public properties, at the very least you ll have no public setters, and all the methods in the aggregate sound more like actions, if you have methods such as AsDto(), that definitely means you are doing something wrong. Also you are loosing all properties that you needed for the read side of things, for example if you had an Order aggregate root, do you really need that OrderItems collection? you have access to that collection through the OrderQueryService.

The term CQRS, evolved from CQS(Command Query Separation) there is a CQS definition from  Meyer, that is very similar but it’s separating methods that change state, since the emphasis is on messages for CQRS, this was an important distinction.[[ref](http://codebetter.com/blogs/gregyoung/archive/2009/08/13/command-query-separation.aspx)]

To prepare for the talk I m also preparing an example (more later), the interesting thing is that, I find that using CQRS and Event Sourcing, I find myself asking questions about the system and the domain, and that is great, because it makes you focus on what the system should do, not the how.

That brings me to another important definition.


## What is Event Sourcing?


Event sourcing means that you capture changes to an application state as a sequence of events ([definition by Fowler](http://martinfowler.com/eaaDev/EventSourcing.html)) . Imagine most systems your worked with up to now, If you had a customer, and they moved, you would probably go to the user interface (web or whatever), go to some sort of customer edit screen, change the details, and thats it, most likely this would trigger an update operation in a normalized database, and unless there was a specific requirement, you’ve not only lost the previous value of the address, also, you dont know if the customer actually moved or if the address was incorrect, so you are loosing history and intent, two very valuable assets.

An important detail about this way of storing data is that its an **append only model **, because you are only adding, the write operation its simpler, this means it takes less time. Another consequence of an append only model is that to change something, we would apply compensating actions.  Interestingly, once the events are stored they are immutable.

If this is such a great way to store data then how come we are not using it everywhere? you might ask. Well there is the problem of having to replay all events to build an aggregate root each time you need to work on it, and hey, what if it’s a very busy one, and there are millions of events to replay. For that, we would use snapshots, i.e. every so often we would record the current state of the aggregate root as is and then when we need to get the aggregate root, we would have  to find the latest snapshot, and then replay any outstanding events to get to up to date. The real culprit is the fact that selecting the top 3 orders where the customer name is Bob, is kind of hard. However, since we are using Event sourcing on the write side and we   might just get away with it .

Event Sourcing is a big theme, the Event store is one of the most complex parts of using CQRS/ES. There are a few open source implementations out there. [Olivers](http://jonathan-oliver.blogspot.com/2010/07/cqrs-event-store.html) comes to mind


### References and Sources


[CQRS and Event Sourcing – Gregg Young](http://codebetter.com/blogs/gregyoung/archive/2010/02/13/cqrs-and-event-sourcing.aspx)

[Clarified CQRS – Udi Dahan](http://www.udidahan.com/2009/12/09/clarified-cqrs/)

[Domain Driven Design Website](http://domaindrivendesign.org/)

[Command Query Separation – Gregg Young](http://codebetter.com/blogs/gregyoung/archive/2009/08/13/command-query-separation.aspx)
