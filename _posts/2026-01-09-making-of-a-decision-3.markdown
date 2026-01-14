---
date: 2026-01-16 00:12:00
last_modified_at:  2026-01-14 00:12:00
layout: single
title: The Making of a Decision - Part 3 - Tools for groups
categories:
- software architecture
- architectural decision
- making of a decision
- decision-making
- tools
excerpt: "Part 3 of a series exploring decision making in software teams. Tools to help you navigate decision making. "
image: "/images/2025/kp-ada-talk.png"
tags: [ software architecture, knowledge-management, knowledge-sharing, decision-making, software-development]
---

This series covers the topics described in [this talk](https://www.youtube.com/watch?v=Ie97Oe-t8Wk). This is part 3 of the series about architectural decision making in software systems. 

* [The Making of a Decision - Part 1]({% post_url 2025-09-01-making-of-a-decision %})
* [The Making of a Decision - Part 2 - Knowledge]({% post_url 2025-11-19-making-of-a-decision-2 %})
* The Making of a Decision - Part 3: Tools for Decision Making - Tools for groups (this post) 
* More coming soon


Part 1 of this series explored how power shapes organisational and architectural decision making by reviewing definitions, laws of power and more. Part 2 covered concepts and models relating to Knowledge, what we mean when we say we known something and who has the right to know things. 

In this post, we will leverage what we learned and turn to tools that helps to use these concepts in practice. The following is not a comprehensive list. These are tools I'm familiar with that helped me with getting a better understanding of the problems or addressing some of the problems.

I decided to group these tools by size of group that it affects as this means the tools would be used by different roles
As I introduce a tool, I will give an overview , explain how these tool relates to the topics discussed and provide links to more in depth research, these are threads for you to pull. 

## Across teams

### The Architecture Advice Process

#### Overview

The Architecture Advice Process is easy to remember and not so simple (yet very rewarding) to implement. From the book:

> A single rule: anyone (a development team member or someone playing a cross-team architecture role) can take (select a decision option) and communicate an architectural decision as long as during the option-making stage, they seek advice from:
>
>    Everyone who will be meaningfully affected by the decision
>Architecture Advice Process
>    People who have expertise in the area in which the decision is being taken


Learn more:

* 📖 Book: [Facilitating Software Architecture](https://facilitatingsoftwarearchitecture.com/). 
* 🗒️ A post:  [Scaling the Practice of Architecture, Conversationally](https://martinfowler.com/articles/scaling-architecture-conversationally.html)
* 📹 A video: [A Commune in the Ivory Tower: A New Approach to Architecture - Andrew Harmel-Law](https://www.youtube.com/watch?v=zp9Go2ChAdw)
* 👩‍💼 Case studies
  * [Decentralizing the Practice of Architecture at Xapo Bank](https://martinfowler.com/articles/xapo-architecture-experience.html)
  * [Architecture Advice Process implementation, The Architect’s Dilemma: What to Do When You Disagree With a Team’s Decision](https://virtualddd.com/facilitating-archdes/architects-disagreement-team-decision/)

A related book worth checking out is [Continuous Architecture in Practice](https://continuousarchitecture.com/). The book provides practical guidance on making architectural decisions incrementally, aligning architecture with agile and DevOps practices, and keeping architecture relevant in fast-moving development environments. 

#### Why use this tool? In the context of better decision making

The Architecture Advice Process can help organisations by giving guidance on how to implement ideas that are already familiar to most, but many are familiar with how to apply them (which is where we can see most failure). You can expect: 

* Rebalancing the power dynamics of decision making. If you are curious about what is like to introduce this practise? See [Elena Stojmilova experience](https://virtualddd.com/facilitating-archdes/team-led-architecture-advice-process/)
* Continuous Knowledge Sharing with a specific focus. Either per decision (ADR, AAF) or per principle.
* Learning possibilities by actively making decisions or by listening and reading about how decisions are made.

### Team Topologies

#### Overview

Team Topologies is an approach that helps with designing teams and their interactions to improve knowledge flow. It aims to increase team flow by focusing on cognitive load and how and when handovers happen.
By defining four forms of teams and three modes of team interactions, Team Topologies encourages healthy interactions that allow teams to provide a steady flow of valuable software. 

Having these simple patterns available to discuss team forms and their interaction help with having a clear language to talk about current state as well as possible alternative future states. 


Learn more:
* 📖 Book: [Team Topologies](https://facilitatingsoftwarearchitecture.com/). 
* 🗒️ A post: [Team Topologies Key Concepts](https://teamtopologies.com/key-concepts)
* 📹 A video: [Monoliths vs Microservices is Missing the Point - Start with Team Cognitive Load - Matthew Skelton & Daniel Pais](https://teamtopologies.com/videos-slides/2019/07/10/monoliths-vs-microservices-is-missing-the-point-start-with-team-cognitive-load-does-eur-2019)

#### Why use this tool, in the context of better decision making

* Team Autonomy. It is non trivial to find design teams, this technique helps with creating autonomous teams that are aligned on value creation.
* Knowledge sharing in teams with high autonomy is high. specifically modelling knowledge flow


### EventStorming

#### Overview

EventStorming is a collaborative domain modelling tool that helps groups of people to understand business flows. It's perfect for kicking off strategic activities and getting a group of up to 30 people to get in-depth understanding of a domain. It has three well known forms: Big Picture, Process Modelling and Design for different kinds of settings.

See below a timelapse of big picture EventStorming 
<video style="max-width: 100%; height: auto;" controls autoplay loop muted>
  <source src="{{site.images}}/2026adaconf-2025-workshop-timelapse.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

Learn more:

* 📹 A video: [50,000 Orange Stickies Later - Alberto Brandolini](https://www.youtube.com/watch?v=1i6QYvYhlYQ)
* 📖 Book: [Introducing EVentStorming](https://leanpub.com/introducing_eventstorming)
* 🗒️ A post: [OPL: Event Storming](https://openpracticelibrary.com/practice/event-storming/)

Another great book on this is [The EventStorming Handbook](https://leanpub.com/eventstorming_handbook) by Paul Rayner.

#### Why use this tool, in the context of better decision making

* It's a great tool for knowledge flow in larger numbers. Probably the fastest way to establish current state
* Learn about the forrest and the trees from and to a group. It allows you to learn both about details and about the big picture.
* When there is power issues, they tend to surface, 

* Synchronising Fragmented Knowledge. EventStorming forces participants from different backgrounds to build a consistent timeline together, ensuring no single person’s incomplete version of the story dominates the decision.Probably the fastest way to establish current state.
* Surfacing and Resolving Contradictions Early. EventStorming uses "hotspots" to visually highlight friction, contradictions, and areas where stakeholders may have inconsistent or incomplete information.
* Power and strong missalignments surface. The workshop's "voting phase" tends to show what the participants truly prioritise. the participants tend to be key stakeholders, this helps validating waht the important problems to solve should be. also everyone is still in the room so it can be discussed


## More to come...
Hope you enjoyed this post about tools to help with architectural decision making.
Next post is about tools for a smaller group of people, think a two pizza team.

