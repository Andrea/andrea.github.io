---
date: 2025-11-19 00:12:00
layout: single
title: The Making of a Decision - Part 2
categories:
- software architecture
- architectural decision
- making of a decision
- knowledge
excerpt: "Part 2 of a series exploring decision making in software teams. From solo programming freedom to complex team coordination, understanding organisational knowledge is essential for effectiveness. "
image: "/images/2025/kp-ada-talk.png"
tags: [ software architecture, organisational-power, workplace-dynamics, decision-making, software-development]
---

This series goes over the topics described in [this talk](https://www.youtube.com/watch?v=Ie97Oe-t8Wk).


This is part 2 of the series about decision making in software systems. The rest of the series

* [The Making of a Decision - Part 1]({% post_url 2025-09-01-making-of-a-decision %})
*  The Making of a Decision - Part 2 - This article
*  The Making of a Decision - Part 3: Tools for Decision Making (coming soon)


Part 1 of this series explored how power shapes organisational and architectural decision making, see items related to the right side of the diagram below. This article focuses on the left side of the diagram,  knowledge. We say we need to know and understand the context to build systems, however What does it mean to know something?

![ingredients-of-a-decision]({{site.images}}/2025/kp-ada-talk.png)


> "Knowledge sharing is (an essential task of) systems building" 
[Post from 2023]({% post_url 2023-03-31-knowledge-sharing-as-systems-building %})

## Understanding Knowledge: The DIKW model

### The DIKW Pyramid

When I was preparing this talk, I spoke with [Dawn Ahukanna](https://www.linkedin.com/in/dawnahukanna/) who introduced me to the DIKW pyramid as good starting model for knowledge.

The DIKW model makes it clear that context is the bridge between data and insight. Data turns into information only when it's interpreted within a relevant context, and it becomes knowledge when that information is applied repeatedly to gain experience. At the top of the pyramid sits wisdom, the least developed layer, demanding moral deliberation and the ability to apply knowledge across situations.

![Data Information Knowledge Wisdom Pyramid]({{site.images}}/2025/dikw-p.png)

### Applying DIKW: A Practical Example

This model might be a good starting point for everyday decision making. Say, the news that a library your organisation heavily depends on has changed its licence.

* Data. The facts: for example, the licence change in the next version introduces a large fee for usage in commercial settings.

* Information. Adding context. The raw facts are then interpreted and linked to the organisation’s own environment. For example this could highlight that, in the near future, the organisation will be liable to pay a significant amount to keep using this library. Not only do members of the organisation understand what changed, but also where it matters, when it will start affecting the system and why.

* Knowledge. Understanding and gaining deeper insights. With the contextualised information in hand, some of these activities would probably follow:
    * Doing a survey of alternative libraries to find viable drop‑in replacements
    * Estimating the cost of replacing the library across the organisation
    * Considering security risks associated with onboarding a new library
    * Looking back at a similar licence change and its effects
    * Discussing with product owners, operations, finance, etc to understand acceptable service interruption or other disruptions
These activities would help build a coherent body of knowledge: the organisation now knows why the change is problematic, how severe the impact could be, and what realistic options exist.

* Wisdom. Judgement informed by values and strategy over time.   From the knowledge the organisation is able to exercise broader judgement; for example it might consider:
    * Creating policies. To avoid future vendor lock‑in, and another to monitor critical dependencies on a regular cadence
    * If migration to a new library is necessary, providing default paths while recognising that this might not suit all teams and preparing for the extra cost in time and money
    * Notifying customers, if it is deemed essential, with a brief notice explaining the migration and reaffirming the commitment to security and reliability
    * Updating the dependency‑management operating procedure. Reviewing whether a mandatory licence‑compatibility check should be required whenever a major version bump is announced

Wisdom here blends technical facts with ethical, financial and strategic considerations, producing a holistic stance rather than a reactionary fix.


For an extensive analysis of the DIKW pyramid please see: [The wisdom hierarchy: representations of the DIKW hierarchy- Jennifer Rowley Bangor Business School, University of Wales, Bangor, UK](https://www.academia.edu/38656728/The_wisdom_hierarchy_representations_of_the_DIKW_hierarchy).

The DIKW model gives us a structure for understanding knowledge, but it raises an important question: who is doing these activities of transforming data into (eventually) wisdom? They are called **Knowledge Workers**.


### Knowledge Workers

People who create software systems are knowledge workers. It's very likely the person reading this is a knowledge worker.

> Knowledge workers are workers whose main capital is knowledge. These are workers whose job is to "think for a living".
source: Thinking For A Living: How to Get Better Performance and Results From Knowledge Workers. Davenport, Thomas H. (2005).

Our output is primarily thinking, the artifacts we create are in support of that thinking. Our capital, our stock, is knowledge. 

If our main capital is knowledge how does our knowledge system work?

## A Systems lens

It is surprising that as we are building software systems, we rarely think systemically about our own knowledge. Diana Montalion addresses this in her book [Learning Systems Thinking](https://learningsystemsthinking.com/).
She invites us to consider that:

*Knowledge Stock*: This refers to the store of knowledge a knowledge worker has developed or can access. Knowledge workers are individuals whose profession involves being "paid to think"

*Knowledge Flow*: This is defined as the "ability to transfer knowledge between people and people and systems in ways that change and shift the system in an effective way"

As an industry we tend to highly value the _stock_ of knowledge, and not so much _flow_. However without knowledge flow it would be impossible to build systems. And not just that, reading further on this I found out that it was essential to innovation.


### Innovation

Most organisations actively pursue innovation in what makes them unique, as a way to insure their growth and longevity. Given how critical innovation is to organisational survival, researchers have extensively studied what actually makes organisations innovative. Multiple papers examine the relationship between knowledge sharing and innovation, the results are consistent. As one study clearly spells it out

> "Knowledge transfer among employees is thought to be crucial determinant of an organisation's capacity to utilise new knowledge and innovate."

Source: Relationships between knowledge inertia, organizational learning and organization innovation by Shu-hsien Liao, Wu-Chen Fei, Chih-Tang Liu

As an industry, we have known for many decades that the need for knowledge transfer  is essential to build and  maintain complex  software systems

## Historic lens: Continuity of the "Theory"

Peter Naur's seminal paper from 1985, *Programming as Theory Building*, talks about the importance of people carrying the theory of the program or system. 

> " Thus, again, the program text and its documentation has proven insufficient as a carrier of some of the most important design ideas"
Source: Peter Naur, Programming as Theory Building 

I want to stress the fact that here we are talking about core design ideas of a program.

The paper continues:

> "The conclusion seems inescapable that at least with certain kinds of large programs, the continued adaptation, modification and correction of errors in them, is essentially dependent on a certain kind of knowledge possessed by a group of programmers who are closely and continuously connected with them."  
Source: Peter Naur, Programming as Theory Building 

Forty years ago we already established the importance of stable teams to keep the program theory, especially needed as we are building more and more complex and complicated systems. 



## The Hidden Barrier: Who Gets to Know? 

Throughout this article, we've discussed how knowledge transforms into wisdom and flows through organizations. Do organisations accept knowledge from everyone within?  whose knowledge is deemed legitimate in the first place?

This isn't just an ethical concern, it's a practical one that directly impacts decision quality. As Iris Meredith explores in ["Who has permission to know things?"](https://deadsimpletech.com/blog/epistemology), corporate epistemology determines which voices are heard and which expertise is valued. When organizations systematically invalidate knowledge they don't just create workplace frustration, they cut themselves off from crucial insights.

> "Knowledge is largely defined and controlled by those in power"

This structural barrier is why many organizations experience sudden "explosions"—accumulated resentment and overlooked expertise finally surfacing when problems become unavoidable. Building better decision making systems requires us to consciously examine: whose knowledge are we excluding, and what is that costing us?



## Resources and extra reading materials


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

### Previous Posts
- [Knowledge sharing is systems building](link) - Post from 2023

## Conclusion

Learning and understanding knowledge has helped me make better decisions. I've long held the intuition that a key indicator of an organisation's health is the time its people dedicate to learning, particularly when they learn together about their systems

I hope you enjoyed the second part of "The making of a decision", if you have ideas on how it could be better please let me know. The next post will be about tools that we can use to improve our decision making in terms of knowledge and power.

