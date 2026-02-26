---
date: 2026-02-21 00:12:00
last_modified_at:  2026-02-26 00:12:00
layout: single
title: Bytesize Architecture Sessions for DDD Discovery
categories:
- software architecture
- tools
- domain-driven-design
- bytesize-architecture-sessions
excerpt: "Using Bytesize Architecture Sessions for DDD Starter Modelling process - Discovery. Create a baseline model of what your current system is at. Example with a few teams "

tags: [ software architecture, discovery, domain-driven-design, Bytesize-Architecture-Sessions, c4]
---


The DDD Starter Modelling Process is an excellent guide when iterating through the design process. 

I have been using Bytesize Architecture Sessions in a few of the sections of the DDD modelling process and I noticed that I had not documented this anywhere. This post aims to address that, starting with [Discovery](https://github.com/ddd-crew/ddd-starter-modelling-process/blob/master/README.md#discover). 

![DDD Starter Modelling Process]( {{site.images}}/2026/ddd-crew-modelling-process--circles.png) 
[DDD Starter Modelling Process by DDD-Crew](https://github.com/ddd-crew/ddd-starter-modelling-process)


Discovery is an essential step of DDD, skipping it undermines every decision that follows. When domain knowledge is shared widely, the team builds a collective understanding that leads to software aligned with the domain and capable of evolving with the business. This step opens the door for more team members to bring forward real innovation into the product.

Starting Discovery with [EventStorming](https://www.eventstorming.com/#styles) is a great way to understand the system in terms on what domain experts truly care about, how the system behaves through time and so much more. 

After EventStorming, it's useful to understand the current structural shape of your system, as it is right now. The best way to do this, in my experience, is running Bytesize Architecture Sessions. 

The way systems currently are organised heavily shape how people think about them and what is possible.

##  Running Bytesize Sessions: A Practical Walkthrough for a smaller team, for the first time

If you work with a cross functional team of ten people or less then, the infographic below should inform the high level of the format we are about to follow.

![Bytesize Architecture Sessions Infographic]({{site.images}}/2026/BAS-infographic.png)



* Teach the participants about [C4](http://c4model.com). C4 is a simple, hierarchical and, easy to learn modelling tool
   ![C4 Infographic]({{site.images}}/2026/C4infographic.png)

* State the **goal of the session**. The goal should be to "Create a System Context Diagram of the system as it **currently is**". Check for questions, ensure everyone is able to participate (e.g they have paper and markers ). Ask attendees to confirm they understand the goal and that everyone attending is expected to create a diagram
* **Alone Together**. Set up a timer for 5 minutes. All attendees create a diagram. When the timer elapses, everyone listens as each person describes their diagram without interruptions
* **Convergence**. With the context from the previous step, create one System Context diagram that that is the convergence of all ideas
* **Introspection**. Five introspective minutes to consider what each participant thought of the session. I generally run this as a fast mini-retro

It highly likely that the individual diagrams will vary significantly. A common pattern, especially for those less familiar with C4, is to have different levels of abstraction present in the diagram. It's important to remember that the goal of running Collaborative Design sessions like this is to grow understanding together. Participating and co-creating is the outcome, the picture we create is a tool to help the participants retrace their steps. 
With this context in mind, plan for some extra sessions in a week or so. 

* **Iterate**. With the context above in mind, run more one hour sessions. Let participants see the effect of iteration, how they can point at something in the diagram and understand how it got to the current state


For this setup, the format online or in person is pretty similar. Please see the [tools section](https://bytesizearchitecturesessions.com/tools/#online) of the Bytesize Architecture Sessions website for more info on this.

> Participating and co-creating is the outcome, the picture we create is a tool to help the participants retrace their steps. 

## Running Bytesize Sessions: A Practical Walkthrough for Bigger Systems

Bigger systems tend to have more people involved. The most common case is when there are 3 to 5 teams working on a system. The teams might represent Engineering for the whole company or, for bigger organisations, they might be a department. 

Engage with the organisation's leadership to learn about who to invite. It would generally depend on:

* Overall team size
* Ensuring the right level of cross‑functional representation, including Engineering, QA, Design, Product, and Operations (especially teams handling configuration changes or customisation work)

Required:
* For a group this size a dedicated facilitator is needed. 
* For an in person event, a room large enough to comfortably accommodate all participants. 
* The room should have tables seating five people each
* Access to a big screen or, alternatively as many large whiteboards as tables.

Once this has been agreed, and with a date set, the following is a representative set of steps to run the first event:


*  **Logistics**.  In person, setup tables for up to 5 people per table. Once everyone has arrived, redistribute people so that each table has a variety of roles and team membership 
*  **Teach C4**. A short overview is best, see infographic above. Mention that they are going try this in the next few minutes

*  **Goal of the session**. It's the same as in the case above create a context diagram of the system as it is right now. Make sure to mention that when the timer starts everyone individually will create a diagram and that when the timer elapses they will have to explain the diagram to the rest of the table
*  **Alone together**. Start the timer. Five minutes is a good default. At this point the room should be silent. When the timer elapses, reiterate that each member of a table need to explain the diagram they created to others. Everyone else in the table is expected to listen and hold the questions and comments until everyone is done
*  **Convergence**. Set a timmer for twenty minutes. On a per table basis, once everyone is done explaining their individual diagrams,  they have to create one diagram together. This means they need to find what makes sense to the whole table
*  **Show and Tell**. Since there are many tables, we task the table with sharing the diagram that they've got to so far. A great practice is to ask the person that knows least about the system to talk about this. Set another timmer for 3 minutes and task the groups to clean up the diagram and help prepare the speaker to share what was learned. Once the timer is finished the facilitator takes pictures of these diagrams and displays them on a big screen , or if there is whiteboards the whole group walks to each of the whiteboards
    It's usual that the diagrams are very different looking, many times the language is generic, or the words used to describe the system are different. When the boundaries are very unclear, the abstractions between system and container will be blurry. The key is for the participants to understand and bring the abstractions that they know of, to the fore

*  **Introspection**. Use sticky notes and a timer to run a short retrospective for the group at large. Identify themes and discuss. Maximum ten minutes long.

The steps above described an in person event. To facilitate this online I strongly recommend an experienced facilitator. 

### Outcomes

You might be wondering why should you go to all this trouble. After roughly one hour, the participants:

* Created together a model of what they think their system looks like. If there are unanswered questions or a non finished diagram, the type of questions and how the diagram is not complete will give everyone very good ideas about the type of knowledge that is missing.
* Shared what they know about their systems. 
* Heard different perspectives and incorporated them into the model they created together
* Learned and got hands on experience with a modelling technique, in this case C4
* Have a picture to help them jog their memory of this experience.  Doing the work collaboratively is like going on a holiday, and that the pictures we take while on holidays (unless you are a photographer) are a lot about being able to recall the experience.
* Are perfectly setup to continue iterating into deeper insights. For most significant work, a handful of Bytesize Architecture Sessions will help you complete a System context and container diagram. For each session, review the guest list (perhaps not everyone is suitable for the container diagram, for example)


With time, and assuming you adopt the practice with some cadence, you will see the following effects

* People know where to go for advice when designing a new non-trivial thing
* People learn that no-one knows everything, improved psycological safety 
* the designs become more nuanced, as People get better at modelling
* people want to learn more DDD (sorry, not sorry)


## Common Anti‑Patterns 

* Staying on a rabbit hole for too long, sometimes you need to document what is being discussed and move on towards the goal 
* frustration because "not finished"
* Treating Bytesize as a meeting instead of a learning loop
* Don't plan the goal of the next bytesize session, last responsible moment is the way to go with this

## Making Bytesize Sessions a Habit

* It's great to have a kick off session, it takes some encouragement to turn Embedding them into team cadence
* Using them as a safe space for questions
* Keeping sessions fun and open.  

## Conclusion: Keep the Practices Short and Sweet

Kicking off a design initiative generally brings a high level of uncertainty, Bytesize Sessions help by creating a safe space for design in deliberate manner. 
Creating shared models help reduce risk and increase clarity. I have shared what works for me, I encourage you to try it and see how you it works for you, perhaps certain aspect of this practice needs to be adapted in some way. I would be very happy to hear about it.


I hope this has helped, if you are organising a session like this and have questions please do reach out. Next post will describe how to use Bytesize Architecture Sessions for [Define](https://github.com/ddd-crew/ddd-starter-modelling-process/blob/master/README.md#define). 
Until the next time.