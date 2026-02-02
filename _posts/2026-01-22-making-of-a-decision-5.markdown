---
date: 2026-02-02 00:12:00
last_modified_at:  2026-02-02 00:12:00
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

This series covers the topics described in [this talk](https://www.youtube.com/watch?v=Ie97Oe-t8Wk). This is part 3 of the series about decision making in software systems. 

* [The Making of a Decision - Part 1]({% post_url 2025-09-01-making-of-a-decision %})
* [The Making of a Decision - Part 2 - Knowledge]({% post_url 2025-11-19-making-of-a-decision-2 %})
* [The Making of a Decision - Part 3 - Tools for groups]({% post_url 2026-01-09-making-of-a-decision-3 %})
* [The Making of a Decision - Part 4 - Team and Personal Tools]({% post_url 2026-01-19-making-of-a-decision-4 %})
* The Making of a Decision - Part 5 - Introducing Decision KP Maps  - This post


Part 1 of this series explored how power shapes organisational and architectural decision making by reviewing definitions, laws of power and more. Part 2 covered concepts and models relating to Knowledge, what we mean when we say we know something and who has the right to know things. Part 3 and 4 covered decision-making tools for different group sizes. This is a post that introduces **Decision KP Map**, the tool I created as result of learning and discussing so much about the subject.


# What is Decision KP Map? 

The process of making a decision involves people that are able to make change and people that have some knowledge on the matter, sometimes people have both (or neither) and can make a difference in the decision. 
This type of mapping I'm proposing, is something you already do intuitively. Mapping, will help you better understand:

* The interactions between the people and the decision 
* The dynamic aspect of the relationship between people involved and,
* Developing patterns and what to do about them


> Decision KP Map is a mapping tool that helps visualise the **subjective** perception of the community that enables decision making.The **Key People**, in terms of their **Knowledge and Power**. Both concepts together are the source of KP in the name, key people and their knowledge and power.

### Examples 

Below you'll find an example map where I added people from history and people's roles to help you see a baseline.

![Decision KP Map Example]({{site.images}}/2026/decision-kp-map-default.png)


Please notice:

* Capability to make change. The horizontal axis denotes the spectrum from **Can't** to **Can** ...make change happen. It's common to conceptualise this as influence, power, etc. A common mistake here would be to only focus in hierarchy, which is am incomplete version of these concepts. This is why I ask the modeller (you?) to think about who can make change happen (in the  given context) as this is a better question to answer. 
First, notice that certain people can make change. Then, you can start thinking about the reason why.  
* Valid and/or accepted knowledge and information.  The vertical axis denotes the spectrum of accepted or valida knowledge: From **Doesn't have** to **Have** ...accepted or valid knowledge. In your discussions about decision who do you think knows about this particular decision in depth? Do they know about this particular decision? How did they visibly contribute to the knowledge pool. The common mistake here is to always think of some person that has a lot of domain knowledge or a more senior position but we don't take into account the real source of the knowledge.  

* **People position**. Where do you position people depends on your subjective understanding. What is important is that the whole map is self consistent. A good way to do this is place all the people and then check that all the people are placed somewhere that makes sense when comparing it with others in the map, for example you might think: JP knows as much as QW about this subject, AR is nearly as able to make change as RB but just not as much.


To make it easier to learn, I added people from history to this map. Also some roles as a way to show the range of the map. 


* **Katherine Johnson**  @ Crewed NASA space flights team. My knowledge on her role is based on reading online about her work after seeing the film [Hidden Figures](https://en.wikipedia.org/wiki/Hidden_Figures). We can understand that she was uniquely capable as well as extremely limited in capability to make change due to social and cultural constraints. If I had to add her to a map she will be where I place her, in the top left quadrant.
* **Don Syme @ F# Programming Language Project** . Don has the most knowledge about the F# programming language project as well as complete control over the direction of the language... as far as I know. If we were drawing a map about who we should probably involve when it comes to changes to the F# programming language, it would be a good idea to:
    a. Attempt to validate that Don has the authority assumed and,
    1. If not correct, good to know, also Don would still have a lot of knowledge and influence on the project. You definitely want to ask for advice when it comes to decision making in this space. It might be someone you add in some maps and omit on others. 

* **Intern**. An intern is someone that is trying to learn the profession, even if a particular intern is extremely capable, it would be irresponsible to not supervise their work and take either their knowledge or capability to make change for granted.  
* **Propaganda writer**. Please remember this is an example, very few people within companies act this way on purpose. If you ever had do interact with someone that is writing a piece that is either disinformation(deliberately hiding the truth) or misinformation(incorrect but not clear if deliberate) the result has similar outcomes. It's harder to make decisions when people like this are in the mix. They might have sufficient capability to make change to push outcomes towards their agenda based on information you know or suspect to be incorrect. 



### How does it work? A simple example

To further understand how to create and read a map, please see the following map and description

![Initial state]({{site.images}}/2026/d-kp-map1.png)

* **Upper Portion**. The map shows D.P, an Engineer, who has a great deal of knowledge about the decision. This knowledge is accepted and, as far as you know, correct. They also have some ability to make change happen. Although BL outranks D.P, D.P has slightly more capability to influence change in the context of this decision.

    Also in this part of the map is BL, a Principal Engineer, who has slightly less knowledge and slightly less capability to make change on this decision.

* **Left Side**. Moving down the vertical axis, we see KJ, an Intern who knows roughly half as much as BL about the subject of the decision and has very little leverage.

* **Middle Right**. At a similar level of accepted knowledge, we have MP, who has some capability to make change in this context. We also have GZ, an Engineering Manager, who has a great deal of capability to make change happen but does not have much knowledge about the decision.

* **Lower Middle Right**. Finally, we have RH, an Engineering Manager with about the same level of capability to make change as MP. However, their knowledge is incorrect and outdated, and they did not show curiosity about validating it during this interaction.



Note: The shape of this map is a common pattern that often appears during unexpected technical incidents, where decisions require coordination between those who understand the problem and those who are positioned to make decisions about it.


Continuing with the example, a few days have elapsed and things have changed. How? The map below depicts a meeting where things have changed slightly since last time.

What happened: 
* BL asked MP, someone GZ respects at a technical level, to have a chat with GZ about this decision. This had the effect of levelling up GZ's knowledge as well as increasing MP's capability to make change, due to the influence increase oon GZ. 
* It improved BL's capability to make change slightly as GL brokered the conversation between MP and GZ

![After a few days ]({{site.images}}/2026/d-kp-map2.png)



## Strengths


* Highlight misalignments. Mapping is a tool to prompt reflection, help you guide stakeholder engagement and discussion, and improve collaboration in organisational decisions. It also helps you question your [ladder of inference][argyris].

* Dynamic Tracking. Repeated use helps with capturing the dynamic interactions of the decision, which is essential in decision processes.
* Clear and easy to learn. The core idea is easy to grasp. and does not require deep technical skills or complex software.
* Discover patterns. Over time, it can help discover some basic patterns and biases of individuals across decisions. On patterns: When someone enters the room, everyone stops sharing knowledge, or maybe they don't talk about certain subjects. These might be essential to the making of this decision. 
* Scale up your leadership team. Mapping can help those new to leadership to navigate decisions making, perhaps initially with some coaching. Many people who write code (roles and titles vary) enter decision‑making with a significant level of technical knowledge but limited understanding of how the rest of the decision‑making process works. This tool can help them.

## Limitations

* Ideal for decisions with less than 15 stakeholders (too hard to track otherwise)
* It takes time to map, especially when on back to back meetings . Can become a practice when doing it for a specially hairy thing / at the end of the day
* Lack of digital support. Experienced mappers might not feel this pain so much, but for those new to tools like this it can be overwhelming.

## How to start mapping? Paper or Online


* **Offline**. Paper is a low friction solution and preferred by many, not so easy to share the maps but possible. 
    * For names, use initials or some code name and a reference page that you can easily move around.  Sticky notes with bluetack has worked well for me)
    * If you are adding anything that is not a person to the map, sometimes people add arrows or extra context, add it in a different colour than the people.
* **Online**: 
    * Any online board (Miro, tldraw, FigJam, etc) will support this. 
    * A board per decision - Use the problem statement until a decision has been made. Then rename to the problem statement
    * I use a colour per person if the group is small. if two people represent a group I use the same colour
    * I tend to copy the last map and move whatever is needed in the new map.
* Some people have requested digital support for this tool. It might be worth building, tho to do that I would love to know that some of you would use it. Please try mapping with existing tools first and let me know what's missing. 



### Other uses 

* Retrospectives or Project kick-off sessions. I can imagine some scenarios where this might work extremely well, I can also imagine this being a disaster. This is why I advocate this as a solo tool 
* Teaching people who are levelling up. This was mentioned by most of the people trying this tool. 
* Share with others what you think it's happening


## More to do

These are some areas I haven't had the chance to investigate yet:

* **Scaling the practice**. Decision KP Maps are ideal for decisions that involve ~20 people. It becomes harder to map when mapping more people  in cross-functional groups.
* **Pair subjective view with data driven metrics**. To investigate, this is a subjective tool. How could it be used along other feedback and data-driven mechanisms? If you are a manager and keen to try this tool and have ideas on how to mix both I am so keen to talk to you 
* **Structured guidance on interpretation**. So you mapped the meetings and feel like you missing something? It would be great to have guidance on how to read the maps, I hope to write on this and also want to encourage you to do it if you are mapping. The difficulty here is when different people map the same pattern, they do so a little bit differently. A great example of this is the "CxO or [HiPPO](https://www.launchnotes.com/glossary/hippo-in-product-management-and-operations) bomb". I like to think of this as "the pattern zoo". For example how does it look like when a HiPPO 🦛(highest-paid person's opinion) enters the conversation? What subject brings the elephant 🐘 into the room? 
* **How to use it in sense making scenarios?** I believe it could be useful in some particular settings in kick-off workshops? However this is something that needs to be tested.

If you are curious about any of these and would like to try the tool either with or without my guidance, please [reach out]() I would be very happy to hear about it.


## Conclusion 

Through this series we dived into rich concepts, practical examples and tools or models to imrpove the process of making a decision.


[argyris]: https://en.wikipedia.org/wiki/Chris_Argyris#Work