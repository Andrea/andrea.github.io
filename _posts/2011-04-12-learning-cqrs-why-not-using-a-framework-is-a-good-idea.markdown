---
author: roundcrisis
comments: true
date: 2011-04-12 11:55:32+00:00
layout: post
slug: learning-cqrs-why-not-using-a-framework-is-a-good-idea
title: Learning CQRS. Why not using a framework is a good idea
wordpress_id: 794
---

I ve been talking to some people over the past few months about CQRS, particularly CQRS/ES and at some point of the conversation I get the **framework **question.

I think the implementation of the patterns CQRS and ES is not trivial (it's also not necessary to do both , but lets keep going) however, the escence of the advantages you get out of both comes from implementing the rules of the domain, in the domain. By making the state transitions explicit.

The number one reason why you should learn about CQRS without a framework is because, it could cloud your understanding of the domain with artificial constraints. Another important reason is that when you learn by doing, you understand the workings and shortcomings of a particular methodology.

That is not to say that frameworks are bad and you should never use them, but make sure that when you make a decision like that, it is a conscious one.

I remember one day when I was at a talk by Gregg Young, and he said: How many of you use (ms)SQL? How many of you made that conscious choice? (ie to use an relational database for storage) .  I realised then that, I didn't make that choice or considered an option in certain cases, but what scared me the most is that I was making a bunch of assumptions as soon as anyone said "system" , it made me realise that most of those assumptions could blind me into not really considering all the options.
