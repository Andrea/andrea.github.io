---
date: 2026-01-15 00:12:00
last_modified_at:  2026-01-15 00:12:00
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

This is part 3 of the series about the common problems found when making architectural decisions, their underlying causes and how to address some of those issues with tools. This post covers tools for groups, such as across teams.

* [The Making of a Decision - Part 1 - Introduction & Power]({% post_url 2025-09-01-making-of-a-decision %})
* [The Making of a Decision - Part 2 - Knowledge]({% post_url 2025-11-19-making-of-a-decision-2 %})
* The Making of a Decision - Part 3: Tools for Decision Making - Tools for groups (this post) 
* [The Making of a Decision - Part 4 - Team and Personal Tools]({% post_url 2026-01-19-making-of-a-decision-4 %})
* More coming soon


Part 1 of this series explored how power shapes organisational and architectural decision making by reviewing definitions, laws of power and more. Part 2 covered concepts and models relating to Knowledge, what we mean when we say we know something and who has the right to know things. 

In this post, we will leverage what we learned and turn to tools that help to use these concepts in practice. The following is not a comprehensive list. These are tools I'm familiar with that helped me solve issues in the past. Each tool's 'Why use this tool' section explains how it tackles specific decision-making problems at a high level. For more nuance or extra details please see the resources I linked to or send me some comments or questions. 

I decided to group these tools by the size of the group that it affects, as the decision to adopt them is with different roles.
For each tool, I will include an overview, provide links to learn more and explain how the tool relates to the topics discussed.  

As a side note, I wanted to add that describing a tool in a paragraph or so, is very hard. How to make justice to what comes to hundreds if not thousands of hours of work that went into creating these facilitation tools? 

## Across teams

### The Architecture Advice Process

#### Overview

The Architecture Advice Process is easy to remember and not so simple (yet very rewarding) to implement. From the book:

> A single rule: anyone (a development team member or someone playing a cross-team architecture role) can take (select a decision option) and communicate an architectural decision as long as during the option-making stage, they seek advice from:
>
>    Everyone who will be meaningfully affected by the decision
>Architecture Advice Process
>    People who have expertise in the area in which the decision is being taken

Please note that the decision taker is not obligated to agree or follow the advice - they are required to listen and record the advice.  
To support the Architecture Advice Process it's useful to use Architecture Decision Records (ADRs), Architecture Advisory Forum (AAF), collectively sourced Architecture Principles and a Technology Radar.


Learn more:

* 📖 Book: [Facilitating Software Architecture](https://facilitatingsoftwarearchitecture.com/). 
* 🗒️ A post: [Scaling the Practice of Architecture, Conversationally](https://martinfowler.com/articles/scaling-architecture-conversationally.html)
* 📹 A video: [A Commune in the Ivory Tower: A New Approach to Architecture - Andrew Harmel-Law](https://www.youtube.com/watch?v=zp9Go2ChAdw)
* 👩‍💼 Case study: [Decentralizing the Practice of Architecture at Xapo Bank](https://martinfowler.com/articles/xapo-architecture-experience.html)
  

A related book worth checking out is [Continuous Architecture in Practice](https://continuousarchitecture.com/). The book provides practical guidance on making architectural decisions incrementally, aligning architecture with agile and DevOps practices, and keeping architecture relevant in fast-moving development environments. 

#### Why use this tool? In the context of better decision making

The Architecture Advice Process can help organisations by giving guidance on how to implement ideas that are already familiar to most, but many are inexperienced applying them. You can expect: 

* Removing bottlenecks. Both top down architecture and hands-on approaches block on people with authority to make decisions. By rebalancing the power dynamics of decision making it is possible to share expertise and remove bottlenecks. If you are curious about what is like to introduce this practise see [Elena Stojmilova experience](https://virtualddd.com/facilitating-archdes/team-led-architecture-advice-process/) and [The Architect’s Dilemma: What to Do When You Disagree With a Team’s Decision](https://virtualddd.com/facilitating-archdes/architects-disagreement-team-decision/)
* Accountability and responsibility combined. When someone outside a team makes a decision for the team. The implementing team may not feel responsible for the outcome. They might not even implement the decision. This decentralised practice ensures that the person with the  need is also the one accountable for the result. The accountability acts as a necessary brake when required.
* Open access learning. Anyone interested in a decision can read ADRs or attend the AAF to learn more about how a decision happen.

### Team Topologies

#### Overview

Team Topologies is an approach that helps with structuring teams and their interactions by focusing on cognitive load as well as how and when handovers happen. It defines four forms of teams and three modes of team interactions. Having these  patterns available to discuss organisational design helps by providing a clear language to design current as well as possible alternate future states. 


Learn more:
* 📖 Book: [Team Topologies](https://teamtopologies.com/). 
* 🗒️ A post: [Team Topologies Key Concepts](https://teamtopologies.com/key-concepts)
* 📹 A video: [Monoliths vs Microservices is Missing the Point - Start with Team Cognitive Load - Matthew Skelton & Manuel Pais](https://teamtopologies.com/videos-slides/2019/07/10/monoliths-vs-microservices-is-missing-the-point-start-with-team-cognitive-load-does-eur-2019)

#### Why use this tool, in the context of better decision making

* Impact of Conway's law. ".Organizations which design systems are constrained to produce designs which are copies of the communication structures of these organizations." Melvin E. Conway, How Do Committees Invent? Team topologies gives you a tool to leverage this by designing communication structures based on value delivery. 

* Team autonomy. Organising teams is hard, this technique helps with creating autonomous teams that are aligned on value creation. In combination with the Architecture Advice Process this technique can help unblock teams.
* Knowledge sharing within teams with high autonomy is high. Specifically, creating teams to increase knowledge flow is a huge value unlock.


### EventStorming

#### Overview

EventStorming is a collaborative domain modelling tool that helps understand and design complex systems by mapping out  Domain Events on a timeline. It's perfect for kicking off strategic activities and enable a group of people to get in-depth understanding of a domain. It has three well known forms: Big Picture, Process Modelling and Design for different kinds of settings. 

See below a timelapse of big picture EventStorming 
<video style="max-width: 100%; height: auto;" controls autoplay loop muted>
  <source src="/abstracts/adaconf-2025-workshop-timelapse.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

Learn more:

* 📹 A video: [50,000 Orange Stickies Later - Alberto Brandolini](https://www.youtube.com/watch?v=1i6QYvYhlYQ)
* 📖 Book: [Introducing EVentStorming](https://leanpub.com/introducing_eventstorming)
* 🗒️ A post: [OPL: Event Storming](https://openpracticelibrary.com/practice/event-storming/)

Another great book on this is [The EventStorming Handbook](https://leanpub.com/eventstorming_handbook) by Paul Rayner.

#### Why use this tool, in the context of better decision making

* Probably the fastest way for a large group to get cohesive understanding of what the system currently does.
* It allows you to learn both about details and about the big picture.
* When there are power issues, they tend to surface during the workshop. These are visible throughout but they become especially visible in the voting phase of the workshop.
* Synchronising Fragmented Knowledge. EventStorming forces participants from different backgrounds to build a consistent timeline together, ensuring no single person’s incomplete version of the story dominates the decision. Probably the fastest way to establish current state.

## More to come...

I hope you enjoyed this post about tools to help with architectural decision making. I would love to hear from you if you have used these tools, what worked for you and what didn't.
The next post is about tools for smaller groups of people.

