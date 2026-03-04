---
date: 2026-03-03 00:12:00
last_modified_at:  2026-03-03 00:12:00
layout: single
title: Bytesize Architecture Sessions for DDD Discovery
categories:
- software architecture
- tools
- domain driven design
- bytesize architecture sessions
- ddd starter modelling process
excerpt: "Using Bytesize Architecture Sessions for DDD Starter Modelling process - Discovery. Create a baseline model of what your current system is at. Example with a few teams "

tags: [ software architecture, discovery, domain-driven-design, bytesize architecture sessions, starter modelling process, c4]
---


The [DDD Starter Modelling Process](https://github.com/ddd-crew/ddd-starter-modelling-process/blob/master/README.md) is an excellent guide when iterating through the design process. This process [is recommended](https://github.com/ddd-crew/ddd-starter-modelling-process/blob/master/README.md#when-to-use-the-ddd-starter-modelling-process) when planning or following significant change, or when there are changes in terms of personnel. Some good examples: major programme of work, beginning brownfield migration, re-organising teams, etc.

I have been using Bytesize Architecture Sessions in a few of the sections of the DDD modelling process. This article focuses on the [Discovery](https://github.com/ddd-crew/ddd-starter-modelling-process/blob/master/README.md#discover) section of the starter process. 

![DDD Starter Modelling Process]( {{site.images}}/2026/ddd-crew-modelling-process--circles.png) 
[DDD Starter Modelling Process by DDD-Crew](https://github.com/ddd-crew/ddd-starter-modelling-process)

Discovery is about sharing domain knowledge. When domain knowledge is shared widely, the team builds a collective understanding that leads to software aligned with the domain. This enables both the team and the software to evolve with the business. Discovery is an enabling step that opens the door for more team members to bring forward innovation for the product.

## The Discovery Step

In my experience, starting Discovery with [EventStorming](https://www.eventstorming.com/#styles) is a great way to understand the system in terms of what domain experts truly care about, how the system behaves through time, and so much more. 

After EventStorming, it's useful to understand the current structural shape of your system, as it is right now. Use Bytesize Architecture Sessions with C4 to address this.


## Bytesize Architecture Sessions Overview

![Bytesize Architecture Sessions Infographic]({{site.images}}/2026/BAS-infographic.png)

Bytesize Architecture Sessions are a workshop format that helps groups understand the systems they work on. Each session focuses on a specific section of a system. Over multiple sessions, the group will converge on a better shared understanding, develop a consistent vocabulary, and build a foundation for designing the future together.

Each Bytesize Architecture Session lasts between 45 and 90 minutes and has four well‑defined parts: Session Goal, Alone Together, Convergence, and Introspection. You can model your systems using different tools, such as C4, Context Mapping, or the Bounded Context Canvas. For teams new to modelling I recommend starting with C4.


## C4 Overview

[C4](http://c4model.com) is a simple, hierarchical, and easy‑to‑learn modelling tool. It has four key diagrams. They move from high level abstractions of the *System Context* where you think in terms of systems and people, the forest. Then, one level down are *C4 Containers*, the trees. Below that are the *C4 Components*, the branches. And at the most detailed level is the *Code Diagram*, the leaves. This last diagram is customarily generated automatically.

![C4 Infographic]({{site.images}}/2026/C4infographic.png)



##  Bytesize Architecture Sessions for Discovery: A Practical Walkthrough for Smaller Groups

If you work with a cross‑functional team of ten people or fewer, the organisation of Discovery workshops is simpler.
You may start with a *Big Picture* or a *Process Model* *EventStorming* workshop, then run a series of Bytesize Architecture Sessions over a few days to produce a System Context diagram and the chosen Container diagrams together.

It’s best to hold the first session in person, as it's easier to address any issues this way. It will enable better dynamics for questions and gathering feedback. Schedule the subsequent sessions a few days later. 

To kick the series off it's a good idea to explain why the group should be doing this activity and an overview of the format. The goal and the activity should not be a surprise to any of the participants.


### Discovery Kick Off


As the Bytesize Architecture Session aspect of Discovery starts, ensure your participants are prepared:
* Teach all participants about [C4](http://c4model.com). A short explanation with examples works well
* Ensure they have stationary, such as markers and suitably sized paper

Proceed with the workshop:

* **Goal of the session**. State the goal of this session: "Create a System Context Diagram of the system as it **currently is**". Check for questions, ensure everyone is able to participate (e.g they can create a diagram individually). Ask attendees to confirm they understand the goal and that everyone attending is expected to create a diagram
* **Alone Together**. Set up a timer for five minutes. All attendees create a diagram. When the timer elapses, everyone listens as each person describes their diagram without interruptions
* **Convergence**. With the context from the previous step, create one System Context diagram that is the convergence of all ideas. This section is the longest, set up a timer for thirty  minutes. 
* **Introspection**. Five introspective minutes to consider what each participant thought of the session. I generally run this as a fast mini-retro

It's highly likely that the individual diagrams will look different to each other. A common pattern, especially for those less familiar with C4, is to have different levels of abstraction present in the diagram. 
A good diagram is a useful outcome only if all attendees understand and learn why the diagram looks the way it does, and what each item in the diagram represents. It's important to remember that the goal of running *Collaborative Modelling*[^CoMo] sessions like this one, is to grow understanding together. 


> Participating and co-creating is the outcome, the picture we create is a tool to help the participants retrace their steps. 

### Next Sessions

Help participants notice the effects of iteration, how they can point at an item in the diagram and understand how it got to its current state. This is why the **Introspection** step at the end of the Bytesize Architecture Session is so valuable.

The format for each of the following Bytesize Architecture Sessions will be the same as the first one. The goal should change as participants converge on the *System Context Diagram*, and then, on the selected *Container Diagram*. 

Iterating on the diagrams is to be expected. For example, it's common for the *System Context Diagram* to need updates after working on the *Container Diagram*. 

#### Logistics and Tooling

For the next sessions, either the online or in-person format are fairly similar. Please see the [tools section](https://bytesizearchitecturesessions.com/tools/#online) of the Bytesize Architecture Sessions website for more information about options.


## Bytesize Architecture Sessions: A Practical Walkthrough for Bigger Systems

Larger systems tend to have more people involved. The most common case is when there are three to five teams working on a system. The teams might represent Engineering for the whole company or, for bigger organisations, they might represent a department. 

Before diving into the steps, it helps to clarify how people participate. Due to the number of people involved a neutral facilitator is strongly recommended. The facilitator guides the flow of the session, manages time, and ensures balanced participation. Their role is both about keeping the group moving, and creating the conditions for shared understanding. 
Participants with leadership responsibilities join as co‑explorers. They should pay special attention to the language use, how mental models differ across participants and teams, and where boundaries or abstractions are unclear. Noticing and making these explicit is where they can add significant value.

### Before the Sessions

Engage with the organisation's leadership to learn about who to invite. There should be at most twenty five participants present. Consider:
 
* Overall team size
* Cross‑functional representation. Include Engineering, QA, Design, Product, and Operations (especially teams handling configuration changes or customisation work)

With larger groups, it's particularly valuable to do this first session in person, alongside other Design kick off activities. For example, run a *Big Picture* *EventStorming* on day 1 and run this first session on day 2.

In addition to selecting the right participants, a few practical setup considerations are needed for the session to run smoothly:

* For a group this size a dedicated facilitator is needed
* For an in person event, a room large enough to comfortably accommodate all participants. The room should have tables seating five people each
* Access to a big screen, or alternatively as many large whiteboards as tables, or both!
* Duration 90min.

### Discovery Kick Off

Once the date is set, the participants confirmed, and a facilitator in place, the following is a representative set of steps:

*  **Logistics**.  In person, setup tables for up to 5 people per table. Once everyone has arrived, redistribute people so that each table has a mix of roles and team membership 
*  **Teach C4**.  A short overview is best, and the infographic above provides a useful reference. Mention that they are going to try this in the next few minutes
*  **Goal of the session**. It's the same as in the simpler case above: "Create a context diagram of the system as it is right now". Make sure to mention that when the timer starts, everyone individually will create a diagram, and that when the timer elapses they will have to explain the diagram to the rest of the table.
*  **Alone together**. Start the timer. Five minutes is a good default. At this point the room should be silent. When the timer elapses, each member of the table will explain the diagram they created to the rest of the table. Everyone else at the table is expected to listen, withholding questions and comments until everyone is done
*  **Convergence**. Set a timer for twenty minutes. On a per table basis they create one diagram together. 
    *  **Show and Tell**. A candidate from each table presents their diagram to the room. Ideally, the person who knows least about the system. Set another timer for three minutes and task the groups with cleaning up the diagram and preparing the speaker.
    * **What to expect**. It's usual that the diagrams look different from each other. Often the language is generic, or the words used to describe the different parts of the system don't match. When the boundaries very unclear, the abstractions between *System* and *Container* will be blurry. The key is for the participants to understand and bring the abstractions they know of into focus. 

*  **Introspection**. Use sticky notes and a timer to run a short retrospective for the group at large. Identify themes and discuss. Maximum ten minutes long.

The steps above described an in person event. To host this session online, an experienced facilitator is essential. 

### Next Sessions

 Some considerations for the next Bytesize Architecture Sessions

* Revisit the guest list.  Depending on availability and roles they might be more or less suitable. Consider, are the participants able to contribute meaningfully? Does it help them in their role? 
* Have a strategy to make the outcomes of the sessions accessible to the wider organisation and consider a way to gather feedback
* Start each Session with a short review of where you left the last time.  A quick overview is a great way to set the scene, then proceed with the goal
* If hosting online, have a template ready. Include images from the previous Bytesize Architecture Session
* Help participants see the effects of iteration. How they can point at something in the diagram and understand its current state. This is why the **Introspection** step at the end is so valuable

The format of each of the Bytesize Architecture Session will follow the pattern of the infographic above. The goal should change according to how far people converge on the *System Context Diagram* and then, to the selected *Container Diagram*. 

It is possible that after working on the *Container Diagram*, the *System Context Diagram* needs to be updated. This reinforces the idea that the diagrams evolve with the group’s understanding rather than being fixed outputs.


## Outcomes

After a few Sessions the participants have:

* Created a model of what they think their system looks like together. If there are unanswered questions or an unfinished diagram, the type of questions surfaced and how the diagram is not complete will make knowledge gaps visible
* Shared what they know about their systems 
* Heard different perspectives and, ideally, incorporated sections into the model they created together
* Learned C4 with hands-on experience
* A suitable setup to continue iterating into deeper insights.


With time, assuming your organisation or teams adopt the practice, you will see the following effects:

* Participants know this is a time and place for advice when making significant changes. This requires support from leadership to sustain the practice
* Participants learn that no one knows everything. This tends to improve psychological safety 
* Designs become more nuanced, as participants get better at modelling
* Everyone wants to learn DDD 🕶️ 📖 


## Common Anti‑Patterns 


* Staying on one discussion for too long. If participants are staying on a topic and not agreeing, perhaps more context is needed. The impasse can be either addressed offline or in a follow up session focusing on that issue only. At minimum, document the issue precisely, and move on towards the goal
* Focusing on creating the perfect diagram, rather than understanding how the system works
* Frustration because the diagram is "not finished" and the timer elapsed. Some level of discomfort with this is to be expected, however in this case it's important to mention that we are constraining on time rather than completion. Indicate that the focus is on learning, understanding, and not the artifact. The models created are reflective of the systems, and those are never finished either
* Treating Bytesize Architecture Sessions as a meeting instead of a workshop. This can be a problem if there are people that dominate the conversation. These type of issues might require coaching
* Precisely planning a series of Bytesize Architecture Sessions with expected outcomes for each session. The way people collaborate, requires flexibility and meeting participants where they are at. Having a plan is ok as long as the plan can be updated.


## Success Metrics

These can be useful metrics depending on your issues:

* A couple of weeks after a knowledge sharing session, ask participants to explain why a system or decision is the way it is. Not what it does, but **Why**
* Track when new joiners stop needing extra context or ask for validation on decisions. 
* Incident response and diagnostic speeds up. How long does it take to identify the root cause, and how many people need to be involved?
* Track the key-person risk. Identify top N people with the highest domain knowledge concentration in your organisation. Over time, are those same people still the ones with the highest domain knowledge concentration? Why?


## Conclusion

Kicking off a Design initiative generally brings a high level of uncertainty. Bytesize Architecture Sessions help by creating a safe space for design, in a deliberate manner, in short and iterative bursts. 
Creating shared models help reduce risk and increase clarity. I have shared what works for me. I encourage you to try it and see how it works for you. Perhaps certain aspects of this practice needs to be adapted for your context in some way. I would be very happy to hear about it.

The next post will describe how to use Bytesize Architecture Sessions for [Define](https://github.com/ddd-crew/ddd-starter-modelling-process/blob/master/README.md#define). 
Until the next time.


[^CoMo]: Collaborative modelling is an approach experts, practitioners, and end-users, work together to create, refine, and validate models. Leveraging the diverse perspectives and expertise of the participants to enhance the model's accuracy, relevance, and usability. By involving a wide range of contributors,it fosters a deeper understanding of complex systems and promotes shared ownership of the outcomes. (Adapted from https://www.michael-ploed.com/collaborative-modeling)