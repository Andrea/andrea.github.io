---
date: 2025-08-21 00:13:00
layout: single
title: Interesting learning resources - July 2025
categories:
- software architecture
- iteration zero
- ddd
excerpt: "Interesting reads including: ProTime case study, different ways to help understanding programming languages, kickstarting with iteration zero and a way to analyse and evaluate models."
image: "/images/2025/models-rwb.png"
tags: [case study, event storming, software architecture, denotational understanding, operational understanding]
---

Interesting reads including: ProTime case study, different ways to help understanding programming languages, kickstarting with iteration zero and a way to analyse and evaluate models..


* [Scaling Teams with Ownership: A ProTime case study](https://aardling.eu/en/insights/scaling-teams-with-ownership-a-protime-case-study). A great example of using DDD. ProTime faced scaling challenges in 2023 as they grew  across 40 countries. Their initial "feature teams" model—where small teams worked on single features for 4-6 months before moving to different features—began showing stress with unpredictable delivery times, spread-thin domain knowledge, and a "everyone owns everything" mentality that devolved into "no one owns anything." This transformation involved cross-organizational workshops to redefine team responsibilities and ensure teams were involved earlier in the design process. Six months later, teams with stronger domain ownership showed improved delivery predictability, clearer capacity insights, and better alignment between team capabilities and business goals.

* [Operational and Denotational Strategies](https://noelwelsh.com/posts/operational-denotational-understanding/) by  Noel Welsh. Noel is very deliberate when it comes to semantics, and this post really shows it. In this post Noel explores operational and denotational approaches to understanding and exploring programming language concepts.Noel Welsh explores two complementary approaches to understanding and explaining programming concepts: operational and denotational explanations. Operational explanations describe how a program executes step-by-step (like walking through function parameter substitution), while denotational explanations focus on what features mean to programmers at a higher conceptual level (like describing functions as ways to generalize expressions with changeable parts). He demonstrates this with examples ranging from basic functions to advanced concepts like type classes, showing how both types of explanations say the same thing but at different levels of abstraction. Might help both in teaching others, and in self-assessment of one's own understanding.

* [All posts by John Cutler](https://publish.obsidian.md/cutlefish/Welcome). There is no suitable summary to this. I've been visiting this landing page and randomly visiting pages and I learned something every.single.time. 

* [Architecting the uncertain - Getting started with Agile Software Architecture](https://printhelloworld.de/posts/iteration-zero-architecture/) Iteration Zero, C4, Event Storming. This post advocates for Iteration Zero approaches, avoiding the trap of traditional upfront design. Software development is fundamentally a learning process and the author recommends **incremental, iterative architecture work with the whole team participating rather than dividing work into independent packages**. Key activities include understanding system context using C4 diagrams, identifying and rating risks through Risk Storming, understanding business processes via Event Storming workshops, setting up testing infrastructure early, defining quality attributes through scenarios, conducting one-on-one interviews with team members, preparing initial product backlogs through User Story Mapping, building walking skeletons for end-to-end functionality, and maintaining a learning backlog for new technologies and practices. The emphasis throughout is on structured learning rather than big design up front, with the goal of making informed decisions when they're actually needed rather than prematurely constraining the project. 
This post seems related to, but different to a post by [Hazel Weakly](https://hazelweakly.me/blog/home-baked-abstractions-store-bought-implementations/) that I come back to a lot.


* (The Conflict-Intelligent Leader: In these turbulent times learning how to manage disputes is a must. by Peter T. Coleman)[https://hbr.org/2025/07/the-conflict-intelligent-leader?ab=HP-magazine-text-2] I highlighted some choice parts of the 
![Emotional intelligence versus conflict intelligence]({{site.images}}/2025/eiq-ciq.png)

![Good Friday agreement]({{site.images}}/2025/good-friday.png)

* [Critically Engaging With Models by Rebecca Wirfs-Brock & Mathias Verraes](https://wirfs-brock.com/rebecca/blog/2022/09/20/critically-engaging-with-models/) This needs a post of it's own to be honest. I'm sure I'll be quoting part of this in the future. To start with a useful definition of model: 

> "Models, whether for a software system, a development process, diseases, political systems, or otherwise, are a way to look at (a part of) the world. They explain how something behaves and how to modify that behavior. ... Models are reductionist; that is, they only show a selection of the subject they’re describing, and lose something in the process. And models are biased: they implicitly reflect the assumptions, constraints, and values of the model’s author." 

Some of the heuristics, like most really important things, seem really obvious except this is the first time I see them all together in one place:
* If there are two ways of looking at something, look for a third
* Compare different models to figure out what one model adds or omits, emphasizes, or downplays
* Understand the underlying belief system that comes with the model
* Determine whether the model confirms my existing belief system and values, or conflicts with them
* Understand whether the model addresses or solves a problem that I’m interested in solving
* Ascertain whether the model points me to problems I might have but haven’t yet considered

Also 
![alt text]({{site.images}}/2025/models-rwb.png)

the post shows how to apply this ideas with an example. Definitely read and bookmark this.


## To read

* [The Three Kinds of Organizational Power](https://jacobian.org/2021/mar/15/organizational-power/) by Jacob Kaplan-Moss. I did read this, but given the work I'm doing I need to dive deeper on this, thanks Anja Kunkel for sharing this write up with me.

* [Navigating Firestorms: The Imperative of Conflict-Intelligent Leadership in a Turbulent World Open Access](https://direct.mit.edu/ngtn/article/40/1-2/5/123561/Navigating-Firestorms-The-Imperative-of-Conflict)

* 
