---
date: 2025-11-19 00:12:00
last_modified_at: 2025-12-17 03:12:00
layout: single
title: The Making of a Decision - Part 2
categories:
- software architecture
- architectural decision
- making of a decision
- knowledge
excerpt: "Part 2 of a series exploring decision making in software teams. From solo programming freedom to complex team coordination, understanding organisational knowledge is essential for effectiveness. "
image: "/images/2025/kp-ada-talk.png"
tags: [ software architecture, knowledge-management, knowledge-sharing, decision-making, software-development]
---

This series goes over the topics described in [this talk](https://www.youtube.com/watch?v=Ie97Oe-t8Wk) with extra depth.


This is part 2 of the series about decision making in software systems. 

* [The Making of a Decision - Part 1]({% post_url 2025-09-01-making-of-a-decision %})
*  The Making of a Decision - Part 2 - This article
*  The Making of a Decision - Part 3: Tools for Decision Making (coming soon)


Part 1 of this series explored how power shapes organisational and architectural decision making by reviewing definitions, laws of power and more. This article focuses on knowledge. 

We say we need to know and understand the context to build systems, what does it mean to know something? What does it mean to know something in the context of an architectural and system design decision?

![ingredients-of-a-decision]({{site.images}}/2025/kp-ada-talk.png)


> "Knowledge sharing is (an essential task of) systems building" 

[Knowledge sharing is systems building (March 2023)]({% post_url 2023-03-31-knowledge-sharing-as-systems-building %})

## Understanding Knowledge: The DIKW Model


When I was preparing this talk, I spoke with [Dawn Ahukanna](https://www.linkedin.com/in/dawnahukanna/) about my thoughts on this talk and about how I was thinking about knowledge, she introduced me to the DIKW pyramid as a good starting model it.

The DIKW model makes it clear that context is the bridge between data and insight. Data turns into information only when it's interpreted within a relevant context, and it becomes knowledge when that information is applied repeatedly to gain experience. At the top of the pyramid sits wisdom, the least developed layer, demanding moral deliberation and the ability to apply knowledge across situations.

![Data Information Knowledge Wisdom Pyramid]({{site.images}}/2025/dikw-p.png)

### Applying DIKW: A Practical Example

This model might be a good starting point for everyday decision making. For example, imagine you learn that a library your organisation heavily depends on has changed its licence and will soon require a large fee for commercial usage. How can the DIKW model help you guide some of your next steps

* **Data. The facts**.  The licence change to be introduced in the next version includes a large fee for usage in commercial settings.

* **Information. Adding context**. The raw facts are interpreted and linked to the organisation’s own environment. For example, in the near future, the organisation will be liable to pay a significant amount to keep using this library, at this point you should know exactly how much in a given period. Perhaps you would also know the cost of migrating to another library, the figure might not be precise. Not only do members of the organisation understand what changed, but also where it matters, when it will start affecting the system and why.

* **Knowledge. Understanding and gaining deeper insights**. With the contextualised information in hand, some of these activities would probably follow:
    * Conducting a survey of alternative libraries to find viable drop‑in replacements
    * Estimating the cost of replacing the library across the organisation
    * Considering security risks associated with onboarding a new library
    * Looking back at a similar licence change and its effects within the organisation
    * Discussing with product owners, operations, finance, etc to understand acceptable service interruption or other disruptions

These activities would help build a coherent body of knowledge: the organisation now knows why the change is problematic, how severe the impact could be, and what realistic options exist.

* **Wisdom. Judgement informed by values and strategy over time**. Based on knowledge, the organisation is able to exercise broader judgement leveraging their people. At this point you might consider:
    * Creating policies. To avoid future vendor lock‑in, and another policy to monitor critical dependencies on a regular cadence
    * If migration to a new library is necessary, provide default paths while recognising that this might not suit all teams and prepare for the extra cost in time and money
    * Notifying customers. if it is deemed necessary, with a brief notice explaining the migration and reaffirming the commitment to security and reliability
    * Updating the dependency‑management operating procedure. Reviewing whether a mandatory licence‑compatibility check should be required whenever a major version bump is announced

Wisdom here blends technical facts with ethical, financial and strategic considerations, producing a holistic stance rather than a reactionary fix.


For an extensive analysis of the DIKW pyramid please see: [The wisdom hierarchy: representations of the DIKW hierarchy- Jennifer Rowley Bangor Business School, University of Wales, Bangor, UK](https://www.academia.edu/38656728/The_wisdom_hierarchy_representations_of_the_DIKW_hierarchy).

The DIKW model gives us a structure for understanding knowledge. The people involved in deriving it are  **Knowledge Workers**.


## Knowledge Workers

People who create software systems are knowledge workers. It's very likely the person reading this is a knowledge worker .

> Knowledge workers are workers whose main capital is knowledge. These are workers whose job is to "think for a living".

source: Thinking For A Living: How to Get Better Performance and Results From Knowledge Workers. Davenport, Thomas H. (2005).

Our output is primarily thinking, the artifacts we create are in support of that thinking. Our capital, our stock, is the things we know. In the context of an organisation, knowledge work is applying knowledge in such way that solves perceived or real customer problems.

Given that our main capital is knowledge, how is it shared, and how can we reason about using it in the most useful and innovative ways?

## A Systems Lens

As Donella Meadows wrote in her book Thinking in Systems: 

>"A system stock is just what it sounds like: a store, a quantity of material or information that has built up over time. It may be a population, an inventory, the wood in a tree, the water in a well, the money in a bank… Stocks change over time through the actions of flows, usually actual physical flows into or out of a stock–filling, draining, births, deaths, production, consumption, growth, decay, spending, saving. Stocks, then, are accumulations, or integrals, of flows."

It is surprising that as we are building software systems, we rarely apply systemic concepts to our problems, including knowledge management. Diana Montalion addresses this in her book [Learning Systems Thinking](https://learningsystemsthinking.com/). In chapter 6, she invites us to consider:

**Knowledge Stock**: This refers to the store of knowledge a knowledge worker has developed or can access. 

**Knowledge Flow**: The ability to transfer knowledge between people and people and systems in ways that change and shift the system in an effective way.

As an industry we tend to highly value the *stock* of knowledge, and not so much *flow*. However without knowledge flow it would be impossible to build systems. And not just that, reading further on this I found out that it was essential to innovation.

### Innovation

Most organisations actively pursue innovation in what makes them unique, as a way to insure their growth and longevity. Given how critical innovation is to organisational survival, researchers have extensively studied what actually makes organisations innovative. Multiple papers examine the relationship between knowledge sharing and innovation, the results are consistent. As one study clearly spells it ou

> "Knowledge transfer among employees is thought to be crucial determinant of an organisation's capacity to utilise new knowledge and innovate."

Source: Relationships between knowledge inertia, organizational learning and organization innovation by Shu-hsien Liao, Wu-Chen Fei, Chih-Tang Liu

As an industry, we have known for many decades that the need for knowledge transfer is essential to build and  maintain complex software systems

## Historic Lens: Continuity of the "Theory"

Peter Naur's seminal paper from 1985, *Programming as Theory Building*, talks about the importance of people carrying the theory of the program or system. 

> " Thus, again, the program text and its documentation has proven insufficient as a carrier of some of the most important design ideas"


I want to stress that the paper focuses on core design ideas of a program. 

The paper continues:

> "The conclusion seems inescapable that at least with certain kinds of large programs, the continued adaptation, modification and correction of errors in them, is essentially dependent on a certain kind of knowledge possessed by a group of programmers who are closely and continuously connected with them."  

We've known for over forty years that stable teams are essential to maintaining the program theory, especially important as systems grow more complex. Yet as an industry, we keep repeating the same Sisyphean cycle, and act surprised each time the boulder rolls back down. Strangely, we do this in the name of cost effectiveness.  


## The Hidden Barrier: Who Gets to Know? 

Throughout this article, we've discussed how knowledge transforms into wisdom and flows through organisations. Do organisations accept knowledge from everyone within?  whose knowledge is deemed legitimate in the first place?

This is an ethical concern and it's a practical concern too that directly impacts decision quality. As Iris Meredith explores in ["Who has permission to know things?"](https://deadsimpletech.com/blog/epistemology), corporate epistemology determines which voices are heard and which expertise is valued. When organisations systematically invalidate knowledge they don't just create workplace frustration, they cut themselves off from crucial insights.

> "Knowledge is largely defined and controlled by those in power"

This structural barrier is why many organisations experience sudden "explosions", accumulated resentment and overlooked expertise finally surfacing when problems become unavoidable. Building better decision making systems requires us to consciously examine: whose knowledge are we excluding, and what is that costing us?


## Conclusion

The DIKW model provides a useful framework for moving from data to wisdom.
Understanding knowledge workers and the importance of knowledge flow matters for innovation and outcomes, yet many organisations have yet to fully grasp this. At the intersection of knowledge and power sits a crucial question: whose knowledge is accepted? When changing an entire organisational culture proves difficult, recognising the barriers to knowledge sharing offers a practical starting point.
Stable teams are essential for preserving the "theory", or domain knowledge, of a system. When seeking better ways to manage information, preventing its loss in the first place is remarkably efficient.


As a side note, I've long held the intuition that a key indicator of an organisation's health is the time its people dedicate to learning, particularly when they learn together about their systems, and keep thinking of ways to validate or invalidate this intuition. If you have thoughts or comments about this or anything to do with this article please let me know  
I hope you enjoyed the second part of "The making of a decision". The next post will be about tools that we can use to improve our decision making in terms of knowledge and power.


## Resources and Extra Reading Materials


### Core Concepts
- [The wisdom hierarchy: representations of the DIKW hierarchy- Jennifer Rowley Bangor Business School, University of Wales, Bangor, UK](https://www.academia.edu/38656728/The_wisdom_hierarchy_representations_of_the_DIKW_hierarchy) This paper revisits the Data–information–knowledge–wisdom (DIKW) hierarchy by looking at how different textbooks explain the hierarchy in a number of widely read textbooks, and analysing their statements about the nature of data, information, knowledge, and wisdom.

- [Programming as Theory Building](link) - Peter Naur (1985). Seminal paper on the importance of maintaining program theory through stable teams.

- [Learning Systems Thinking](https://mentrixgroup.com/mentrix-school-of-systems) - Diana Montalion. Explores systemic approaches to knowledge in organizations.

### Knowledge and Power
- [Who has permission to know things?](https://deadsimpletech.com/blog/epistemology) - Iris Meredith. Explores how corporate epistemology and power structures determine whose knowledge is valued.


### Decision Making
- [Slow down to speed up your decision-making](https://virtualddd.com/sessions/slow-down-to-speed-up-your-decision-making-gien-verschatse/) - Gien Verschatse


### Related Research
- [Relationships between knowledge inertia, organizational learning and organization innovation](link) - Shu-hsien Liaoa, Wu-Chen Fei, Chih-Tang Liu. On knowledge transfer as a determinant of innovation capacity.

- [Charisma in Everyday Life: Conceptualization and Validation of the General Charisma Inventory](https://www.researchgate.net/publication/318667785_Charisma_in_Everyday_Life_Conceptualization_and_Validation_of_the_General_Charisma_Inventory) - Konstantin O. Tskhay et al., University of Toronto.


