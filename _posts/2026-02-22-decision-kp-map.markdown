---
date: 2026-02-28 00:12:00
last_modified_at:  2026-01-28 00:12:00
layout: single
title: Decision KP Maps - More stuff
categories:
- software architecture
- architectural decision
- making of a decision
- decision-making
- tools
excerpt: "Part  of a series exploring decision making in software teams. Introducing Decision KP Map. Examples and how to use."
tags: [ software architecture, knowledge-management, knowledge-sharing, decision-making, software-development, decision-kp-map]
---



The process of making a decision involves people that are able to make change and people that have some knowledge on the matter, sometimes people have both (or neither) and can make a difference in the decision. It’s very likely that you already do some version of this map in your head. By mapping you should be able to better understand:

* Your perception of the interactions between the people and the decision
* The dynamic aspect of the relationship between people involved and,
* Developing patterns and what to do about them


### Decision KP Map

Below you'll find an example map where I added people from history and people's roles to help you see a baseline.

![Decision KP Map Example]({{site.images}}/2026/decision-kp-map-default.png)


Thing I want you to notice:

* **Can / Can not make change happen**. The horizontal axis denotes the capability to make change. Generally people with management roles tend to be able to make change happen. At the same time other people might also be able to make change happen. In this diagram it's more important to notice that they can make change, then we can start thinking about the reason why . Could be due to role authority, charisma, influence or maybe you don't really know why but when this person wants something then it happens.
* **Has accepted or valid knowledge**. The vertical axis is about knowledge and information. In your discussions who do you think knows about this particular decision in depth? Nuance is very important here, they might know a lot about other things but not about the subject of whatever you are mapping. 

* **People position**. Consider that the boxes with names denote the top right corner (X marks the spot). Where do you position people depends on your subjective understanding, the important thing is that the whole map is consistent with what you experience


Example people, I added people from history. Also some roles as a way to show the range of the map. 


* **Katherine Johnson**  @ Crewed NASA space flights. My knowledge on her role is based on reading online about her work after seeing the film [Hidden Figures](https://en.wikipedia.org/wiki/Hidden_Figures). We can understand that she was uniquely capable as well as extremely limited in capability to make change due to social and cultural constraints. Hence why she is in the top left quadrant.
* **Don Syme @ F# Programming Language Project** . Don has the most knowledge about the F# programming language project as well as complete control over the direction of the language... as far as I know. If we were drawing a map about who we should probably involve when it comes to changes to the F# programming language, it would be a good idea to:
    1. Attempt to validate that Don is the right person to talk to and,
    1. Even if not correct, Don would have been someone you definitely want to ask for advice when it comes to 

* **Intern**. Even if a given intern is extremely capable, it would be irresponsible to take either their knowledge or capability to make change for granted, at least until you know better. 
* **Propaganda writer**. Please remember this is an example, very few people within companies act this way on purpose. If you ever had do interact with someone that is writing a piece that is either disinformation(deliberately hiding the truth) or misinformation(incorrect but not clear if deliberate) the result has similar outcomes. It's harder to make decisions when people like this are in the mix. They might have sufficient capability to make change to push outcomes towards their agenda based on information you know or suspect to be incorrect. 



Decision KP Map is a mapping tool that helps visualise the **subjective** perception of the community that helps make a decision, the **Key People**, in terms of their **Knowledge and Power**. Both concepts together are the source of KP in the name, key people and their knowledge and power. Power is a tricky thing to think about and map so you will notice that the horizontal axis is all about the range in making change happen, which is a lot easier to think about. It's where you can place your understanding of where people sit in terms of:
* How much accepted knowledge they can access and,
* How much change they are able to effect. 

A Decision KP Map always has a specific context, for example an architectural decision. Over the course of a decision, one would generate multiple maps. People can be added or removed as needed. 


## A decision viewed as maps 




Mapping is not just about what **you** consider to be accepted knowledge (see [Who gets to know]({% post_url 2025-11-19-making-of-a-decision-2 %}/#the-hidden-barrier-who-gets-to-know) ) worth sense checking to see if others in the community if decision-makers also react the same way.

## Other people testing it, key comments

* Mostly I asked people that have a similar role to mine. Most of us are Principals, Staff+, Architects

Bruno
* Helped me compare the "hierarchy versus the real conversation" 
* Capture a controversial statement and understand the impact
* CxO bomb
    * maps to surface the unspoken rules




### Other uses

* Teaching people that are levelling up. This was mentioned by most of the people trying this tool. 
* Share with others what you think it's happening
* Retrospectives or Project kick-off sessions. I can imagine some scenarios where this might work extremely well, I can also imagine this being a disaster. This is why I advocate this as a solo tool 


## More to do

* ideal for small, close-knit groups but was a bit harder to apply at scale e.g. decisions involving >15 stakeholders and cross-functional groups.
* To investigate, this is a subjective tool. How could it be used along other feedback and data-driven mechanisms? If you are a manager and keen to try this tool and have ideas on how to mix both I am so keen to talk to you 
* Structured guidance on interpretation. So you did the maps but now you are not sure what to do with it? ... giving guidance is hard because people map quite differently
* how to use it in sense checking scenarios? maybe during some particular parts of workshops? what would be good / bad


## Good things about it

* "Effective in highlighting misalignments (e.g., those with power but little knowledge or vice versa) and can serve as a lightweight tool to prompt reflection, guide stakeholder engagement and discussion, and improve collaboration in organizational decisions." - Aaron Sempf, CTO APAC for AWS

* Clear and easy to learn: The core idea is easy to grasp. and does not require deep technical skills or complex software.
* Dynamic Tracking: Repeated use after meetings allowed me to capture evolving dynamics, which is essential in real-world decision processes.
* Encourages Pattern Recognition: Over time, it supported the discovery of a few basic behavioural patterns (and biases of individuals across decisions) and recurring bottlenecks.

## Problems with it

* ideal for decisions with less than 15 stakeholders (too hard to track otherwise)
* It takes time to map, especially when on back to back meetings . Can become a practice when doing it for a specially hairy thing / at the end of the day
* Lack of digital support


## Feedback from others using this tool

I felt it was important to get feedback from others before writing about this tool




#### Why use this tool, in the context of better decision making

* Understand what happened during an exchange (e.g. a meeting). An easy to learn tool that helps evaluate your [ladder of inference][argyris]
* Teach people new to leadership how to navigate decisions. Many people who write code (roles and titles vary) enter decision‑making with a significant level of technical knowledge but limited understanding of how the rest of the decision‑making process works. This tool can help them.


### A brief history

The more time I spent learning about about all these topics, the more others and myself spent time discussing these topics and dealing with everyday problems, I found myself starting to map the relationships between people in a lightweight fashion and it was the brilliant [Dawn]() who helped me realise this was a tool as she said something like I used your map, and then she pointed to  the diagram I ve been drawing over to talk about some point

