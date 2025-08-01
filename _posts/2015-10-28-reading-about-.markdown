---
date: 2015-10-28 19:13:00
layout: single
classes: wide
title: Reading about primes, type providers and more
categories:
- programming
- development
- primes
- type-providers
- fsharp
---

Some stuff I have been looking at today that you might find interesting

* [Having fun with type level numbers by using a type provider](http://gettingsharper.de/2014/12/19/having-fun-with-type-level-numbers-using-a-type-provider/)
Excellent post that I have been meaning to read about implementing a type provider for primer numbers, complete with the explanation on primes and type provider implementation. Really the *making illegal states unrepresentable* .

* [Nested looping to programmatic depth in F#](http://latkin.org/blog/2014/12/26/nested-looping-to-programmatic-depth-in-f/) This post comes to a solution to the lack of _break_ and _return_ in F## by solving the similar problem we did in a recent [Functional Kats meetup](http://www.meetup.com/FunctionalKats/events/225465966/) The first time I thought when I saw the problem was, oh this is about [Computation expressions](fsharpforfunandprofit.com/posts/computation-expressions-intro/) but although there is a link to a solution by Tomas Petricek that [uses them](http://tomasp.net/blog/imperative-i-return.aspx/) this post shows a different approach that shows better performance 66ms versus 880ms.  

* [Eve project](https://github.com/witheve/Eve) you might agree with they ideas behind it or not, but it is worth checking out this project about trying to help us think, while also changing the way we write code. Eve: Better tools for thought http://witheve.com



Yours BatmAndrea

![view]({{ site.images }}/2015-cadiz.jpg)
