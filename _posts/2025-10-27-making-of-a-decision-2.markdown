---
date: 2025-10-27 00:12:00
layout: single
title: The Making of a Decision - Part 2
categories:
- software architecture
- architectural decision
- making of a decision
- knowledge
excerpt: "Part 2 of a series exploring decision making in software teams. From solo programming freedom to complex team coordination, understanding organisational power isn't academic—it's essential for effectiveness. "
image: "/images/2025/kp-ada-talk.png"
tags: [ software architecture, organisational-power, workplace-dynamics, decision-making, software-development]
---

This series goes over the topics described in [this talk](https://www.youtube.com/watch?v=Ie97Oe-t8Wk).


This is part 2 of the series about decision making in software systems. The rest of the series

* [Part 1]({% post_url 2025-09-01-making-of-a-decision %})
* [This article]



After talking a little about power definitions, the items on the right side of this diagram, now lets discuss knowledge, what it means to know something.

![ingredients-of-a-decision]({{site.images}}/2025/kp-ada-talk.png)



> "Knowledge sharing is (an essential task of) systems building" 


## DIKW Pyramid

When I was preparing this talk, I had a chat with [Dawn Awkuna](https://www.linkedin.com/in/dawnahukanna/) she mentioned the DIKW pyramid. Which is a model I was not familiar with. 

An initial look shows something we see implicitly across many texts: it isn’t just about collecting facts (data) but about interpreting them (information) and integrating them into mental models (knowledge).

It also highlights the role of context; raw data is not very useful until it has a context. Wisdom sits atop the hierarchy, good decisions require more than facts, they need judgement and ethical considerations. It is the application of knowledge over time in a human mind, with human judgement and values at the core of wisdom.

![Data Information Knowledge Wisdom Pyramid]({{site.images}}/2025/dikw-p.png)

This model might be a good starting point for everyday decision‑making. Say, the news that a library your organisation heavily depends on has changed its licence.

    * Data. The facts: for example, the licence change in the next version introduces a fee for usage in commercial settings.

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
        * Updating the dependency‑management operating procedure—reviewing whether a mandatory licence‑compatibility check should be required whenever a major version bump is announced

    Wisdom here blends technical facts with ethical, financial and strategic considerations, producing a holistic stance rather than a reactionary fix.

For an extensive analysis of the DIKW pyramid please see:

* [The wisdom hierarchy: representations of the DIKW hierarchy- Jennifer Rowley Bangor Business School, University of Wales, Bangor, UK](https://www.academia.edu/38656728/The_wisdom_hierarchy_representations_of_the_DIKW_hierarchy) This paper revisits the Data–information–knowledge–wisdom (DIKW) hierarchy by examining the articulation of the hierarchy in a number of widely read textbooks, and analysing their statements about the nature of data, information, knowledge, and wisdom




## A Systems lens

1. Knowledge Stock: This refers to the store of knowledge a knowledge worker has developed or can access. Knowledge workers are individuals whose profession involves being "paid to think"
.
2. Knowledge Flow: This is defined as the "ability to transfer knowledge between people in ways that change and shift the system in an effective way"


## Innovation



## Accepted knowledge





## More resources about decision making

* [Slow down to speed up your decision-making – Gien Verschatse](https://virtualddd.com/sessions/slow-down-to-speed-up-your-decision-making-gien-verschatse/)


## Conclusion




I hope you enjoyed the second part of "The making of a decision", the next post will be about tools that we can use to improve our decision making in terms of knowledge and power.
If you have any comments or questions please reach out.
