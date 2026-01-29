---
date: 2026-01-31 00:12:00
last_modified_at:  2026-01-29 00:12:00
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


Part 1 of this series explored how power shapes organisational and architectural decision making by reviewing definitions, laws of power and more. Part 2 covered concepts and models relating to Knowledge, what we mean when we say we know something and who has the right to know things. Part 3 and 4 covered decision-making tools for different group sizes. This is a post that introduces Decision KP Map, the tool I created as I was having deeper discussions about this subject.


The process of making a decision involves people that are able to make change and people that have some knowledge on the matter, sometimes people have both (or neither) and can make a difference in the decision. 
The type of mapping I'm proposing here is something that is very likely you already do some version of in your head. By mapping you should be able to better understand:

* Your perception of the interactions between the people and the decision
* The dynamic aspect of the relationship between people involved and,
* Developing patterns and what to do about them


### Decision KP Map

Below you'll find an example map where I added people from history and people's roles to help you see a baseline.

![Decision KP Map Example]({{site.images}}/2026/decision-kp-map-default.png)


Please notice:

* From **Can't** to **Can** ...make change happen. The horizontal axis denotes the capability to make change. It's common to conceptualise this as influence, power, etc. A common mistake here would be to only focus in hierarchy, which is am incomplete version of these concepts. This is why I ask the modeller (you?) to think about who can make change happen (in the  given context) as this is a better question to answer. 
First, notice that certain people can make change. Then, you can start thinking about the reason why.  
* From **Doesn't have** to **Have** ...accepted or valid knowledge. The vertical axis is about knowledge and information. In your discussions who do you think knows about this particular decision in depth? Do they know about this particular decision? How did they visibly contribute to the knowledge pool. The common mistake here is to always think of some person that has a lot of domain knowledge or a more senior position but we don't take into account the real source of the knowledge.  

* **People position**. In the map above the the boxes have a x at the top right corner (X marks the spot).  Where do you position people depends on your subjective understanding. What is important is that the whole map is self consistent. As in when you finished placing all the people, it makes sense to you.


Example people, I added people from history. Also some roles as a way to show the range of the map. 


* **Katherine Johnson**  @ Crewed NASA space flights. My knowledge on her role is based on reading online about her work after seeing the film [Hidden Figures](https://en.wikipedia.org/wiki/Hidden_Figures). We can understand that she was uniquely capable as well as extremely limited in capability to make change due to social and cultural constraints. If I had to add her to a map she will be where I place her, in the top left quadrant.
* **Don Syme @ F# Programming Language Project** . Don has the most knowledge about the F# programming language project as well as complete control over the direction of the language... as far as I know. If we were drawing a map about who we should probably involve when it comes to changes to the F# programming language, it would be a good idea to:
    a. Attempt to validate that Don has the authority assumed and,
    1. If not correct, good to know, also Don would still have a lot of knowledge and influence on the project. You definitely want to ask for advice when it comes to decision making in this space. It might be someone you add in some maps and omit on others. 

* **Intern**. An intern is someone that is trying to learn the profession, even if a particular intern is extremely capable, it would be irresponsible to not supervise their work and take either their knowledge or capability to make change for granted.  
* **Propaganda writer**. Please remember this is an example, very few people within companies act this way on purpose. If you ever had do interact with someone that is writing a piece that is either disinformation(deliberately hiding the truth) or misinformation(incorrect but not clear if deliberate) the result has similar outcomes. It's harder to make decisions when people like this are in the mix. They might have sufficient capability to make change to push outcomes towards their agenda based on information you know or suspect to be incorrect. 



Decision KP Map is a mapping tool that helps visualise the **subjective** perception of the community that helps make a decision, the **Key People**, in terms of their **Knowledge and Power**. Both concepts together are the source of KP in the name, key people and their knowledge and power.

## Mapping a decision

I will elaborate on the example from [Part 2]({% post_url 2025-11-19-making-of-a-decision-2%}/#applying-dikw-a-practical-example) of this series. 

### Setting the scene

This is a fictional scenario based on some experiences I've have that are close to this. 

**The problem**: A library your organisation heavily depends on has changed its licence and will soon require a large fee for commercial usage.

A setting like this is highly likely to be a little stressful. It is also likely to generate many meetings (some impromptu and others rather formal) and a lot of online interactions (slack, teams chat, email, etc).

I will map here some significant ones. Explain who are the participants and any interesting emerging comments and patterns


### Meeting 0: Initial Library Licensing Change Discovery

Agenda 
* The license change is explained in plain language
* Timeline for enforcement is clarified. 
* Agreement on whether to escalate 
* Agree next steps

## Meeting Summary

* NC, a dev at the TX team shared the news of the change, and learned more about it (details of the licence change, alternatives others started evaluating)
* During a weekly sync meeting I H gave the floor to NC to explain the problem
* CO and CS Present and asked more questions - CO obvs looking at the strategic options company wide
* Not useful comments from LG - the Principal from the MS team. Seems worried about derailing on side project. Confusing and took a lot of time.  
* FJ - The principal from the LS team seemed better informed but she is in bad terms with  both CO and CS
* AT - Product Owner for LS and TX tries to gather more context about immediate impact to in-flow initiatives.
* Pretty much everyone understands we shouldn't panic but we need more info - CS (Eng manager) and AT (Product Owner) will come back to people on who and when can we do this
* A slack channel created 






### Lessons learned - How to create Decision KP Maps for a problem

* Offline: Paper is a low friction solution and preferred by many, not so easy to share. 
    * For names, use initials or some code name and a reference page that you can easily move around.  Sticky notes with bluetack has worked well for me)
    * Anything that is not a box, sometimes people add arrows or extra context, in a different colour than the main.
* Online: 
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
* **Structured guidance on interpretation**. So you mapped the meetings and feel like you missing something? It would be great to have guidance on how to read the maps, I hope to write on this and also want to encourage you to do it if you are mapping. The difficulty here is when different people map the same pattern, they do so a little bit differently. A great example of this is the "CxO or [HiPPO](https://www.launchnotes.com/glossary/hippo-in-product-management-and-operations) bomb"
* how to use it in sense checking scenarios? maybe during some particular parts of workshops? what would be good / bad

If you are curious about any of these and would like to try the tool either with or without my guidance, please [reach out]() I would be very happy to hear about it.

## Strengths

* Effective at highlighting misalignments (e.g., those with power but little knowledge or vice versa) and can serve as a lightweight tool to prompt reflection, guide stakeholder engagement and discussion, and improve collaboration in organizational decisions." 

* Clear and easy to learn: The core idea is easy to grasp. and does not require deep technical skills or complex software.
* Dynamic Tracking: Repeated use after meetings allowed me to capture evolving dynamics, which is essential in real-world decision processes.
* Encourages Pattern Recognition: Over time, it supported the discovery of a few basic behavioural patterns (and biases of individuals across decisions) and recurring bottlenecks.

## Limitations

* ideal for decisions with less than 15 stakeholders (too hard to track otherwise)
* It takes time to map, especially when on back to back meetings . Can become a practice when doing it for a specially hairy thing / at the end of the day
* Lack of digital support. I've started 


#### Why use this tool, in the context of better decision making


* Understand and highlight misalignments. An easy to learn tool that helps evaluate your misalignments and question your  [ladder of inference][argyris].
* Dynamic Tracking: Repeated use helps with capturing the dynamic interactions of the decision, which is essential in real-world decision processes.
* Teach people new to leadership how to navigate decisions. Many people who write code (roles and titles vary) enter decision‑making with a significant level of technical knowledge but limited understanding of how the rest of the decision‑making process works. This tool can help them.


### A brief history

The more time I spent learning about about all these topics, the more others and myself spent time discussing these topics and dealing with everyday problems, I found myself starting to map the relationships between people in a lightweight fashion and it was the brilliant [Dawn]() who helped me realise this was a tool as she said something like I used your map, and then she pointed to  the diagram I ve been drawing over to talk about some point

## Conclusion 

Through this series we dived into rich concepts, practical examples and tools or models to imrpove the process of making a decision.
