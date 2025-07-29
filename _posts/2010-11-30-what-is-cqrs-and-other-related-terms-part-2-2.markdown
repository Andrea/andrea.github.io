---
author: roundcrisis
comments: true
date: 2010-11-30 19:00:47+00:00
layout: single
classes: wide
slug: what-is-cqrs-and-other-related-terms-part-2-2
title: What is CQRS and other related terms - Part 2
wordpress_id: 741
categories:
- cqrs
- ddd
tags:
- cqrs
- event store
- events
- software architecture
---

## CQRS with Event Sourcing


[caption id="" align="alignleft" width="269" caption="Photo By edinburghcityofprint(flickr)"]![Ledger](http://farm3.static.flickr.com/2763/4268190563_6b9a7f840d_z.jpg)[/caption]

Looking at CQRS and Event Sourcing as Architectural patterns, when we use them together the impact of that is widespread. For a start, your aggregates should only be exposing behaviour, and that behaviour is related to the commands that use that aggregate root, actually, the entry point to doing anything in the domain is through a command. (this have implications on how we test, but we’ll talk about that later on).

The aggregate root should now expose only behaviour, encapsulating all state, setters are seeing as a code smell. This change is not a direct consequence of CQRS, however, it was very hard to achieve this without it if doing DDD.

One of the questions I got during the talk was about how to replay perhaps millions of events, without a huge delay, and the answer to that is **Snapshots**, basically you preserve the current state of the aggregate root, serialized . There are a few ways to do snapshots, but the principle is that you get your snapshot, which will be up to a particular version, and then replay any events from that version on ( if there are any).

At the system level, it is important to note that, we now have an explicit state transition, what I'm trying to say is that when your customer (ie the person that comes up with the requirements for the system) sais something like, when a customer is created, then that can be mapped directly to CustomerCreatedEvent ie, there is a close relationship between what happens and what caused the state transition and that can be relevant to the business. This, I think, is the biggest advantage of using CQRS

Since the read storage and the Write storage are logically separated  and they can be physically separated too, that means, that they can have different scaling policies.

Another interesting benefit of using event sourcing is that you have an integration point available, without any extra cost. The integration point could serve a Reporting tool, or an external service, or maybe you just want to push some sort of notifications, these are all easily doable, you have a bus publishing messages…

Actually, the way we are using event sourcing in the above stated scenario implies an eventually consistent model. If interested in this topic, have a look at this blog for the cost of eventual consistency. We ll go through some code and then come back to this topic.

I don’t think I mentioned this yet, but, there is one really awesome thing about this whole thing, and that is that we are framework free, there are a few principles and ideas to learn, but once you got them, there is not really much that you need a framework for, maybe if you want you can have an out of the box event store, they are simple in principle but a bit harder to code that it appears first. There are some frameworks to do CQRS with ES however, the code you need to have a system like this running is not so complex, and understanding how it works is crucial.


### The trail of the Command


Lets forget about the UI for a second and think of a system from the point of: I have a command, and I need to execute it.

Every time you send a command, the system handles the command, more than likely, an aggregate root will be involved and an operation on it will occur, this will result in one or many events being published; once the event(s ) have been published, the subscribers will get this message. One of the subscribers is the Event store, that will append this new event. There are variations of this description but this will do for now. Lets say the


```
public void Handle(CustomerMovedCommand command)
        {
				var customer = _repository.Get&lt;Customer&gt;(command.CustomerId);
				customer.Moved(command.AddressLine1, command.AddressLine2, command.Postcode );
				_repository.Save(customer);
        }
```


the aggregate root (Customer) code for that method could look something like this


```
public void Moved(string line1, string line2, string postcode)
{
    ApplyEvent(new CustomerMovedEvent()
                        {
                            AddressLine1 = line1,
                            AddressLine2 = line2,
                            PostCode = postcode
                        });
}
```




In there we can see that we are applying the event, once we apply the event, we will not only set up the internal properties of the aggregate root(that we need for write operations), also through the repository or other commit like mechanism(we’ll look at this in a sec), we will publish this message, making the event store aware of this new event and making the query side aware of this event too, the query side is then responsible of de-normalizing the data to a suitable shape.

An important thing to note is that the event is declared as something that happened, it is in the past, for example: CustomerMovedEvent, that means that as far as our system is concerned, the customer has moved.

**Next part will include Modelling and testing**

I bundled a few interesting links in this bit.ly bundle** [http://bit.ly/9LC877](http://bit.ly/9LC877) **
