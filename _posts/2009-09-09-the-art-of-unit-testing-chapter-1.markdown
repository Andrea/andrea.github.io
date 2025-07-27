---
author: roundcrisis
comments: true
date: 2009-09-09 09:35:55+00:00
layout: single
classes: wide
slug: the-art-of-unit-testing-chapter-1
title: 'The Art of Unit Testing - Chapter 1 '
wordpress_id: 372
categories:
- alt.net
- unit-testing
tags:
- unit-testing
---

We are meeting for the first time for the Book club and just to get the ball rolling on this I though I'd write up a mini summary of chapter 1 on [The Art of  Unit Testing](http://www.manning.com/osherove/) before the meeting as a way to explore the concepts and then another one after if necesary.

So far I like the book, a very clean and concrete explanation of the basics, in plain english.

Some concept definitions are opinionated, but  Roy does a good job of it by telling you that there are many defintions available of certain terms, he then tells you wich one he will be using, for example when he defines Legacy Code he setteles for: Code that has no unit tests ( in line with M Feathers), he gives you a few other options including one that kept sticking in my head: Code that works. (quite possibly with bugs , I cant help to add).

He makes a lot of emphasis in Good Unit Tests, as tests that are automated, repeatable, easy to implement and read, that are trustworthy and run quickly, normally written using an unit testing framework.

I think a knock on effect of this is that the tests will be just a few lines long and quite likely many.

The definition of Integration Tests made me think a lot. For reference: Integration testing means testing two or more dependent software modules as a group.  I'd really like to discuss this with the group tomorrow today, I'd say many of us do more Integration testing that we tend to think? particularly if we have a dependency on a service that has no other hard dependencies ( like a db, I/O operations or similar)   -- Will update on this.

Another good concept to be introducing at this early stage is the Regression, and when I was reading this I was thinking It's so great to tie this up with CI, why? Well if you have relevant test coverage and you change something (adding the required unit tests and all ) you commit your code , the build machine will immediately go and try to build and run your test suite, so that will help you to know if potentially you have a regression.

He outlines a series of questions to ask yourself  to find out if you are writting good tests the one I liked the most is this one:


> Can I write a basic test in no more than a few minutes? -- Will update on this too later on.


There is a  unit test example without using a  framework, I liked it  first because of this little snippet that I didnt know about: MethodBase.GetMethod().Name , more to the point I think hes trying to highlight the advantages of the frameworks and also because it reminds you of the fact that you dont need unit testing frameworks.

Then there is a basic intro to TDD, where the last D stands for Development , and thats ok, I have not much more to add because I didnt find anything that sticks out .

So far so good, I think we could have jammed the first two chapters in this meet up.

Comments, corrections and questions as always welcome :)
