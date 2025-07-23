---
author: roundcrisis
date: 2022-12-26 12:48:00+00:00
layout: post
title:  Bytesize architecture sessions - Why start with C4 Diagrams
categories:
- collaboration
- software-architecture
- bytesize-architecture-sessions
---

In my previous post about [Bytesize Architecture sessions](http://www.roundcrisis.com/2021/09/28/bytesize-architecture-sessions/) I described briefly that one of the key aspects of the session is to have  time ["Alone together"](http://www.roundcrisis.com/2022/10/01/the-power-of-alone-together) where each of the participants of the session will have a few minutes where they are in the same room **working on the same task, but not collaborating**. 
What I did not mention was what to do. This post fixes that. 

When I started running sessions I noticed that if you ask people to draw the system without any constraints each person draws at different levels of abstraction, some will add a lot of low level details, some will do a bit of high level and a bit of low level... most won't be able to finish which is not ideal.

I suggest drawing what is known as a Context Diagram of the system as is **right now**. A Context diagram is the top level of the [C4 model](https://c4model.com/). C4 is a modeling technique for describing your system at different abstraction 
levels.

If you are wondering why drawing the system as it is right now, these are a few reasons
 * It is important to anchor the diagrams in reality. This means that it's possible to check if the diagrams are correct. 
 * Any architecture effort needs information about the current state of the system, what better place to start than drawing something everyone knows about.


If your team is not familiar with C4,  teach them about it before a Bytesized Session. I find that most teams get there fairly fast with very little coaching.

<img src="https://static.structurizr.com/workspace/76748/diagrams/SystemContext.png" height=300px alt="Example of a Context Diagram. Source: C4model.com">

Example of a Context Diagram. Source: C4model.com

If your system is too big and you think it won't be possible to draw the whole Context diagram in one session, then break it up.
Once you have a Context Diagram, it is a good idea to continue with the other parts of C4, at least do Container and Components. 

