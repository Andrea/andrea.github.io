---
author: roundcrisis
comments: true
date: 2010-06-30 22:00:26+00:00
layout: single
classes: wide
slug: on-pair-programming
title: 'On Pair Programming '
wordpress_id: 597
tags:
- pair-programming
- xp
---

### What is pair programming?


Its when 2 developers sit down together to write a piece of code. There is one person in the keyboard known as the **driver** and another person looking at the code and commenting about it, known as the ** navigator**, these roles can change in time. The idea is that while you are typing you are likely to catch certain things and when you are watching you are to catch other things.


### Why?


I dont know if this happens to you, but many times, when I m not sure how to solve a problem or when I have a solution to a problem that I m not terribly happy with, I will talk to someone else about it. Then, one of two things happen: whoever I talk to gives me an idea, or as I explain the problem I realised that I missed an important piece of the puzzle and find the solution, the hidden third option is that I don't have a solution but I have more to explore.  Anyway the whole point is that verbalizing the problem,  gives you a different take on it; maybe makes it more real?, as you talk you realise that certain things make no sense, you  ask yourself questions.  **You have more visibility and clarity**

Another more obvious advantages is that **two brains are more than one**, collaboration can get you to really far. More eyes looking at the code will at least avoid silly mistakes, in the better cases it will drive you to better design, never mind the fact that two people will know this code really well, we all know that this is really handy in a team ( we all take holidays, have days when our brains just refuse to work, etc).

When pairing , each of the persons in the pair need to be really involved, there is no distractions,  ( so perhaps take breaks every hour and a half or so) this intensity means to me that its more likely that as a pair there are more angles of the problem that will be covered.


### Whats wrong with it?


When people are pairing there are a few things I ve noticed that tend to go wrong

1) **One way street**. One of the pair is hogging the control and the navigator is quiet. This is probably the worse thing. the only possible advantage of this is knowledge transfer but I think this kind of pairing does more bad than good. One way to counter act this is using Test driven Ping Pong (see below). But education is key.

If pairing, then try to pair, not to control.

If  pairing try to collaborate you are not just watching a movie.

If things are going to fast ask for slowing down, its not going to get better if you dont understand.

2)** We'll fix it later**. This is when the pair decide to do something below standard. I dont think its a terrible practise but it does leave a "bad taste" because even when the pair decide the task is accomplished , there is stuff left t do. also there is the broken window problem.


### Test Driven Ping Pong


Given a driver and a navigator, the role changes per test, say we have Alice and Bob, Alice is the driver first, she writes a test, fails, they fix  the code so the test passes, goes green , they come up with some refactorings , then Bob is the driver for the next test and so on. This sounds like a good approach when the developers dont know each other well or they have an ego problem, or they dont know where to start


### Informal Pair Programing


The navigator and driver roles change whenever is necessary, like when discussing stuff on a whiteboard . This is probably the best way but at the same time it requires the pair to be very involved and request changes often. I think this is more Organic(for lack of a better word) and pleasurable.

Any comments on this? i would really appreciate it particularly from people practicing pair programing often
