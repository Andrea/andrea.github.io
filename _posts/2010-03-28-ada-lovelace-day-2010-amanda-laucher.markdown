---
author: roundcrisis
comments: true
date: 2010-03-28 08:57:39+00:00
layout: single
classes: wide
slug: ada-lovelace-day-2010-amanda-laucher
title: 'Ada Lovelace Day 2010: Amanda Laucher'
wordpress_id: 529
categories:
- .net
tags:
- Ada Lovelace Day
- f#
---

I'm late with the Ada Lovelace Day article, I had the choice of making it on time but incomplete, or put some time and be late, and I chose the later this time. I really though the person and the topic deserved in depth investigation.

I didn't really know how to approach the Ada Lovelace Day last year and this year I still don't know now, I think the best homage I can do is learn more about F# in this case.

This post is about Amanda Laucher and about F#. Amanda is the author of [F# in Action](http://www.manning.com/laucher/). A speaker and most importantly a software developer, when you see her talking you can see she really likes what she does, and that fact is pretty inspirational.

I found quite a few of her presentations online



	
  * QCon London 2010 - [Pragmatic F# in Action](http://www.infoq.com/presentations/Pragmatic-F-Sharp-in-Action)

	
  * QCon London 2009 - [Concurrent Programming with F#](http://www.infoq.com/presentations/Concurrent-Programming-with-Microsoft-F-Amanda-Laucher)

	
  * Channel 9  - 2008 Ted [Neward and Amanda Laucher on F#](http://www.dotnetrocks.com/default.aspx?ShowNum=377)

	
  * I'm sure there is more but that'll get you going =)


Then I also found some other F# resources

Wikipedia had a pleasant surprise in store for me with a really comprehensive [introduction to the language](http://en.wikipedia.org/wiki/F_Sharp_(programming_language)), and also pointed me to a [wikibook](http://en.wikibooks.org/wiki/F_Sharp_Programming) however when I started typing the code and trying to run it I ran into problems because the parser looks at line breaks.

**Disclaimer: I never done any f# before so anything below could be completely wrong (if so please let me know so I learn :) )**

In a short time I learnt that

F# is



	
  * Not purely a functional language, some OO aspects and has type inference.

	
  * a strongly typed language

	
  * .Net language

	
  * has Garbage Collection

	
  * does Lazy evaluation ( this is really cool )

	
  * Some sort of Asynchronous workflow ( need to digg deeper on this)


More detail

	
  * Everything is immutable by default, but there are mutable objects ( apparently the objects that you can get by interoping with, say,a  c# dll are mutable but I'm not sure)

	
  * lazy evaluation

	
  * Asynchronous Workflows

	
  * You can pass functions as result of function executions, or be the result of functions, and have functions inside functions

	
  * Send parts of parameters into a function

	
  * have a collection of functions that can be started asynchronously (holy smokes!)


After looking around I also found some good videos from Erik Meyer on the topic, hes got a series of them you can have a look [here](http://channel9.msdn.com/shows/Going+Deep/Lecture-Series-Erik-Meijer-Functional-Programming-Fundamentals-Chapter-1/), the series goes through the history of functional programming and principles, very interesting.

I can see a lot of potential on this, I find functional programming a big mind switch and I'm sure it will take me a good while to do it properly, however, the goodness of looking at this code comes from the ideas you can take from different approaches.

One thing that did strike me so far is that i ve seen bad variable names and no unit testing on it at all, on the other hand, the power that you seem to suddenly have is just incredible, tho since the paradigm shift is so big, I found myself stumbling and not being able to do things that i find really simple in c# (like print an array to the console, the difficulty was on realising that the line breaks are significant)

The real life example from the QCon talk from 2009 was a really good way to see the value of the language as real life usage, the QCon  talk from 2010 was really good because it dived deep into the language, language usage, etc.

I feel like I've started learning something that will change the way I code and I'm really happy about that.
