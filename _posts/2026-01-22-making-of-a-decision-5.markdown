---
date: 2026-02-04 00:12:00
last_modified_at:  2026-02-04 00:12:00
layout: single
title: The Making of a Decision - Part 5 - Introducing Decision KP Maps
categories:
- software architecture
- architectural decision
- making of a decision
- decision-making
- tools
excerpt: "Part  of a series exploring decision making in software teams. Introducing Decision KP Map. Examples and how to use."

tags: [ software architecture, knowledge-management, knowledge-sharing, decision-making, software-development, decision-kp-map]
---

The series covers the topics described in [this talk: The Making of a Decision](https://www.youtube.com/watch?v=Ie97Oe-t8Wk). This is part 5 of the series about decision making in software systems. 

* [The Making of a Decision - Part 1]({% post_url 2025-09-01-making-of-a-decision %})
* [The Making of a Decision - Part 2 - Knowledge]({% post_url 2025-11-19-making-of-a-decision-2 %})
* [The Making of a Decision - Part 3 - Tools for groups]({% post_url 2026-01-09-making-of-a-decision-3 %})
* [The Making of a Decision - Part 4 - Team and Personal Tools]({% post_url 2026-01-19-making-of-a-decision-4 %})
* The Making of a Decision - Part 5 - Introducing Decision KP Maps  - This post


Part 1 of this series explored how power shapes organisational and architectural decision making by reviewing definitions, laws of power and more. Part 2 covered concepts and models relating to Knowledge, what we mean when we say we know something and who has the right to know things. Part 3 and 4 covered decision making tools for different group sizes. This is a post that introduces **Decision KP Map**, the tool I created as result of learning and discussing so much about the subject.


# What is Decision KP Map? 

The process of making a decision involves people that have varying degrees of the capability to make change and people that have varying degrees of knowledge on the matter, sometimes people have both. 
This type of mapping I'm proposing is something you very likely, already do intuitively. Mapping will help you better understand:

* The interactions between the people and the decision 
* The dynamic aspect of the relationship between people involved and
* Developing patterns and what to do about them


> Decision KP Map is a mapping tool that helps visualise your **subjective** perception of the community that enables decision making.The **Key People**, in terms of their **Knowledge and Power**. Both concepts are the reason for the name of this tool .

### Examples 

Below you'll find an example map where I added people from history, and others described by roles to help create a baseline.

![Decision KP Map Example]({{site.images}}/2026/decision-kp-map-default.png)

**How to read this map**

* **Capability to make change**. On the horizontal axis the scale moves from **can’t** to **can** make change happen. You might think of it as  a proxy for influence, power and the like. Avoid fixing your view on hierarchy alone, because that gives an incomplete picture. Instead, answer Who is actually able to bring about change in the given context?
    Begin by recognising the individuals who can make change, then examine the factors that enable them.
* **Valid and/or accepted knowledge and information**.The vertical axis denotes a spectrum from **doesn’t have** to **has** accepted, valid knowledge. While debating decisions, note the individuals with thorough understanding and note how they have actively enriched the knowledge pool. A common pitfall is to always credit the most senior person; instead, recognise the genuine source of the information.

* **People position**. Where you position people depends on your subjective understanding. What is important is that the whole map is self consistent. A good way to do this is place all the people and then check that all the people are placed somewhere that makes sense when comparing it with others in the map, for example you might think: JP knows as much as QW about this subject, AR is nearly as able to make change as RB but just not as much.


To make it easier to learn I have added historical figures to the map, together with a few roles to illustrate its range. 


* **[Katherine Johnson](https://en.wikipedia.org/wiki/Katherine_Johnson)** @ Crewed NASA space flights team. My knowledge on her role is based on reading online about her work after seeing the film [Hidden Figures](https://en.wikipedia.org/wiki/Hidden_Figures). We can understand that she was uniquely capable as well as extremely limited in capability to make change due to social and cultural constraints. If I had to add her to a map she will be in the top left quadrant.
* **[Don Syme](https://en.wikipedia.org/wiki/Don_Syme)** @ F# Programming Language Project. Don has the most knowledge about the F# programming language project as well as complete control over the direction of the language... as far as I know. If we were drawing a map about who we should probably involve when it comes to changes to the F# programming language, it would be a good idea to:
    1. Attempt to validate that Don has the authority assumed and,
    1. If incorrect, Don would still have a lot of knowledge and influence on the project. You definitely would want to ask his advice when it comes to decision making in this space. In a case like this, you might add him in some maps and omit on others. 

* **Intern**. An intern is someone that is trying to learn the profession. Even if a particular intern is extremely capable, it would be irresponsible to not supervise their work and take either their knowledge or capability to make change for granted.  
* **Propaganda writer**. Please remember this is an example, very few people within companies act this way on purpose. If you ever had to interact with someone that is writing a piece that is either disinformation (deliberately hiding the truth) or misinformation (incorrect but not clear if deliberate) the result has similar outcomes. It's harder to make decisions when people like this are in the mix. They might have sufficient capability to make change and push outcomes towards their agenda, based on information you know or suspect to be incorrect. 


### How does it work? A simple example

To understand how to create and read a map, please see the following map and description

![Initial state]({{site.images}}/2026/d-kp-map1.png "Decision KP Map a simple example")

* **Upper Portion**. The map shows DP, an Engineer, who has a great deal of knowledge about the decision. This knowledge is accepted and, as far as you know, correct. They also have some ability to make change happen. Although BL outranks DP, DP has slightly more capability to influence change in the context of this decision.

    Also in this part of the map is BL, a Principal Engineer, who has slightly less knowledge and slightly less capability to make change on this decision.

* **Left Side**. Moving down the vertical axis, we see KJ, an Intern who knows roughly half as much as BL about the subject of the decision and has very little leverage.

* **Middle Right**. At a similar level of accepted knowledge, we have MP, who has some capability to make change in this context. We also have GZ, an Engineering Manager, who has a great deal of capability to make change happen but does not have much knowledge about the decision.

* **Lower Middle Right**. Finally, we have RH, an Engineering Manager with about the same level of capability to make change as MP. However, their knowledge is incorrect and outdated, and they did not show curiosity about validating it during this interaction.



Note: The shape of this map is a common pattern that often appears during unexpected technical incidents, where decisions require coordination between those who understand the problem and those who are positioned to make decisions about it.


Continuing with the example, a few days have elapsed and things have changed. How? The map below depicts a meeting where things have changed slightly since last time.

What happened: 
* BL asked MP, someone GZ respects at a technical level, to have a chat with GZ about this decision. This had the effect of levelling up GZ's knowledge as well as increasing MP's capability to make change, due to the influence increase on GZ. 
* It improved BL's capability to make change slightly as GL brokered the conversation between MP and GZ

![After a few days ]({{site.images}}/2026/d-kp-map2.png "Decision KP Map example after a few days")

## Who is this tool for

This tool is especially helpful for people who are part of the decision making process or who are the decision makers themselves. It’s useful for those who value knowledge in a particular context.

People who do software design, architecture, or have team‑leadership responsibilities are likely to find this tool most useful.

## Strengths


* Highlight misalignments. It's a tool to prompt reflection, help you guide stakeholder engagement and discussion, and improve collaboration in decision making. It also helps you question your [ladder of inference][argyris].
* Dynamic Tracking. Repeated use helps with capturing the dynamic interactions of the decision, which is essential in decision processes.
* Clear and easy to learn. The core idea is straightforward, and does not require deep technical skills or complex software.
* Discover patterns. Over time, it can help discover some basic patterns and biases of individuals across decisions. For example, you might notice that when certain people enter the room, knowledge-sharing stops, or specific topics become off-limits.These might be essential to the making of this decision. 
* Scale up your leadership team. Mapping can help those new to leadership to navigate decision making, perhaps initially with some coaching. Many people who write code (roles and titles vary) enter decision making with a significant level of technical knowledge but limited understanding of how the rest of the decision‑making process works. This tool can help them.

## Limitations

* Ideal for decisions with less than 15 stakeholders. it becomes too hard to track everyone otherwise
* Mapping takes time. Those who would benefit from this tool the most tend to be in back to back meetings 
* Lack of digital support. Experienced mappers might not feel this pain so much, but for those new to tools like this it can be overwhelming.

## How to start mapping? Paper or Online

* **Offline**. Paper is a low friction solution and preferred by many, harder to share. 
    * For names, use initials or some code name and a reference page that you can easily move around.  Sticky notes with bluetack has worked well for me
    * If you are adding anything that is not a person to the map, such as arrows or extra context, add it in a different colour.
* **Online**: 
    * Any online board (Miro, tldraw, FigJam, etc) will support this
    * A board per decision - Name board with the problem statement until a decision has been made. When a decision is made, rename the board to reflect the decision.
    * I use a colour per person if the group is small. if two people represent a group I use the same colour
    * I tend to copy the last map and move whatever is needed in the new map

Some people have requested digital support for this tool. It might be worth building, though to do that I would love to know that some of you would use it. Please try mapping with existing tools first and let me know what's missing. 



### Other uses 

* Retrospectives or Project kick-off sessions. I can imagine some scenarios where this might work extremely well, I can also imagine this being a disaster. This is why I advocate this as a solo tool 
* Teaching people who are levelling up. This was mentioned by most of the people trying this tool
* Share with others what you think it's happening


## More to do

These are some areas I haven't had the chance to investigate yet:

* **Scaling the practice**. Decision KP Maps are ideal for decisions that involve ~20 people. It becomes harder to map when mapping more people  in cross-functional groups
* **Pair subjective view with data driven metrics**. To investigate, this is a subjective tool. How could it be used along other feedback and data-driven mechanisms? If you are a manager and keen to try this tool, I would like to talk to you. Please reach out.
* **Structured guidance on interpretation of the maps**. Decision KP Map users map similar things in different ways, however there are emerging patterns and there is a lot to learn by collecting and sharing them. 
    Some examples that have already surfaced (I'm starting to think of it as the "pattern zoo"): 
    * "CxO or [HiPPO](https://www.launchnotes.com/glossary/hippo-in-product-management-and-operations)🦛 bomb".  What should you look for in your map to detect this situation? Are you the HiPPO?
    * The elephant 🐘 into the room. What does a map look like when someone brings a topic everyone knows to be problematic but it's not possible to discuss? 
* **How to use it in sense making scenarios?** I believe it could be useful in some particular settings, for example in kick-off workshops. However this is something that needs to be tested.

If you are curious about any of these and would like to try the tool either with or without my guidance, please [reach out]() I would be very happy to hear about it.


## Conclusion 

Through this series we dived into rich concepts, practical examples and tools or models to improve the process of making a decision. In this article I have introduced you to Decision KP Maps. What is it, illustrative examples, strengths and limitation of the mapping technique as well as the work planned to grow the tool.
I have been collecting feedback on the tool usage over the last six months and plan to share of the insights from the pioneers using this tool 


[argyris]: https://en.wikipedia.org/wiki/Chris_Argyris#Work