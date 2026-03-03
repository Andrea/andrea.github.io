---
date: 2026-02-21 00:12:00
last_modified_at:  2026-02-26 00:12:00
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


The DDD Starter Modelling Process is an excellent guide when iterating through the design process. [It's recommended](https://github.com/ddd-crew/ddd-starter-modelling-process/blob/master/README.md#when-to-use-the-ddd-starter-modelling-process) when big changes have happened or will be happening in your software systems or, when there are changes in terms of personnel. Some good examples: Major programme of work, beginning brownfield migration, re-organising teams, etc.

I have been using Bytesize Architecture Sessions in a few of the sections of the DDD modelling process, this write up highlights some of the hows and whys and focuses on the [Discovery](https://github.com/ddd-crew/ddd-starter-modelling-process/blob/master/README.md#discover) section of the starter process. 

![DDD Starter Modelling Process]( {{site.images}}/2026/ddd-crew-modelling-process--circles.png) 
[DDD Starter Modelling Process by DDD-Crew](https://github.com/ddd-crew/ddd-starter-modelling-process)

When domain knowledge is shared widely, the team builds a collective understanding that leads to software aligned with the domain and capable of evolving with the business. Discovery is an enabling step that opens the door for more team members to bring forward real innovation into the product.

## The Discovery Step

In my experience, starting Discovery with [EventStorming](https://www.eventstorming.com/#styles) is a great way to understand the system in terms on what domain experts truly care about, how the system behaves through time, and so much more. 

After EventStorming, it's useful to understand the current structural shape of your system, as it is right now. When the people you work with have conflicting or incomplete ideas about the current structure of their systems, the best is running Bytesize Architecture Sessions with C4. 


## Bytesize Architecture Sessions Overview

![Bytesize Architecture Sessions Infographic]({{site.images}}/2026/BAS-infographic.png)

Bytesize Architecture Sessions are a workshop format that helps groups understand the systems they work on. Each session focuses on a specific section of a system. Over multiple sessions, the group will converge on a better shared understanding, develop a consistent vocabulary, and build a foundation for designing the future together.

Each Bytesize Architecture Session lasts between 45 and 90 minutes and has four well‑defined parts: Session Goal, Alone Together, Convergence, and Summary. You can model your systems using different tools, such as C4, Context Mapping, or the Bounded Context Canvas. For teams new to modelling I recommend starting with C4.


## C4 Overview

[C4](http://c4model.com) is a simple, hierarchical, and easy‑to‑learn modelling tool. It has four key diagrams. They move from high level abstractions of the *System Context* where you think in terms of systems and people, the forest. Then, one level down are *C4 Containers*, the trees. Below that are the *C4 Components*, the branches. And at the most detailed level is the *Code Diagram*, the leaves. This last diagram is customarily be generated automatically.

![C4 Infographic]({{site.images}}/2026/C4infographic.png)


##  Bytesize Architecture Sessions for Discovery: A Practical Walkthrough for Smaller Groups

If you work with a cross functional team of ten people or less, the organisation of Discovery workshops should be simpler.
Optionally start with Big Picture or Process Model EventStorming run a series of Bytesize Architecture Session over a few days, to create *System Context* and selected *Container Diagrams* together.  
It's ideal to run the first session in person to have time to address questions and gather feedback. Run the following sessions a few days later. 

### Kick off day

These are some necessary steps to kick the series of, 

* Explain what is happening and why. What is the reason to do Discovery
* Teach all the participants about [C4](http://c4model.com). A short explanation with examples works well.

Proceed with the workshop aspect of the day:

* State the **goal of the session**. The goal should be to "Create a System Context Diagram of the system as it **currently is**". Check for questions, ensure everyone is able to participate (e.g they can create a diagram individually ). Ask attendees to confirm they understand the goal and that everyone attending is expected to create a diagram
* **Alone Together**. Set up a timer for five minutes. All attendees create a diagram. When the timer elapses, everyone listens as each person describes their diagram without interruptions
* **Convergence**.  With the context from the previous step, create one System Context diagram that that is the convergence of all ideas. This section is the longest, set up a timer for thirty  minutes. When the timer elapses move on to the next step.
* **Introspection**. Five introspective minutes to consider what each participant thought of the session. I generally run this as a fast mini-retro

It's highly likely that the individual diagrams will look different to each other. A common pattern, especially for those less familiar with C4, is to have different levels of abstraction present in the diagram. 
A good diagram is a useful outcome only if all attendees understand and learn why the diagram looks the way it does and what each item in the diagram represent.  It's important to remember that the goal of running *Collaborative Modelling*[^CoMo] sessions like this one, is to grow understanding together. 


> Participating and co-creating is the outcome, the picture we create is a tool to help the participants retrace their steps. 

### Next sessions

Help participants see the effects of iteration, how they can point at something in the diagram and understand how it got to the current state. This is why the **Introspection** step at the end is so valuable.

The format of each of the Bytesize Architecture Sessions will be the same. The goal should change according to how far participants converge on the *System Context Diagram* and then, to the selected *Container Diagram*. 

Iteration on creating models is to be expected. For example, it's common for the *System Context Diagram* to need updates after working on the *Container Diagram*. 


### Logistics and Tooling

For this setup, the format online or in person is pretty similar. Please see the [tools section](https://bytesizearchitecturesessions.com/tools/#online) of the Bytesize Architecture Sessions website for more info about options.


## Bytesize Architecture Sessions: A Practical Walkthrough for Bigger Systems

Bigger systems tend to have more people involved. The most common case is when there are three to five teams working on a system. The teams might represent Engineering for the whole company or, for bigger organisations, they might represent a department. As systems grow and more teams become involved, the way people participate in these sessions becomes increasingly important.

Before diving into the steps, it helps to clarify how people participate. Due to the number of people involved a neutral facilitator is strongly recommended. The facilitator guides the flow of the session, manages time, and ensures balanced participation. Theirs is an enabling role, creating the conditions for shared understanding. 
Participants with leadership responsibilities join as co‑explorers. They should pay especial attention to the language use, how mental models differ across participants and teams, and where boundaries or abstractions are unclear. Noticing and making these explicit is where they can add significant value.

### Before the sessions

Engage with the organisation's leadership to learn about who to invite, there should be no more than twenty participants present. It depends on:

* Overall team size
* Ensuring the right level of cross‑functional representation, including Engineering, QA, Design, Product, and Operations (especially teams handling configuration changes or customisation work)
* With larger groups, its particularly valuable to do this first session in person, alongside other Design kick off activities. For example run a Big Picture EventStorming on day 1 and run this first session on day 2.

Required:

* For a group this size a dedicated facilitator is needed
* For an in person event, a room large enough to comfortably accommodate all participants. The room should have tables seating five people each
* Access to a big screen or, alternatively as many large whiteboards as tables, or both


### Kick off day

Once this has been agreed, and with a date set, the following is a representative set of steps to run the kick of Bytesize Session:


*  **Logistics**.  In person, setup tables for up to 5 people per table. Once everyone has arrived, redistribute people so that each table has a variety of roles and team membership 
*  **Teach C4**. A short overview is best, see infographic above. Mention that they are going try this in the next few minutes

Now is time to get the participants involved


*  **Goal of the session**. It's the same as in the case above, "Create a context diagram of the system as it is right now". Make sure to mention that when the timer starts everyone individually will create a diagram and that when the timer elapses they will have to explain the diagram to the rest of the table.
*  **Alone together**. Start the timer. Five minutes is a good default. At this point the room should be silent. When the timer elapses, reiterate that each member of a table need to explain the diagram they created to others. Everyone else in the table is expected to listen and hold the questions and comments until everyone is done
*  **Convergence**. Set a timmer for twenty minutes. On a per table basis, once everyone is done explaining their individual diagrams, they have to create one diagram together. This means they need to find what makes sense to the whole table
    *  **Show and Tell**. Since there are many tables, we task the table to share the diagram that they've got to so far. A great practice is to ask the person that knows least about the system present this to the wider group. Set another timmer for 3 minutes and task the groups to clean up the diagram and help prepare the speaker to share what was learned. Once the timer is finished the facilitator takes pictures of these diagrams and displays them on a big screen , or if there is whiteboards the whole group walks to each of the whiteboards
    It's usual that the diagrams look different to each other. Often times the language is generic, or the words used to describe the different parts of the system don't match. When the boundaries very unclear, the abstractions between system and container will be blurry. The key is for the participants to understand and bring the abstractions they know of, to the fore. 

*  **Introspection**. Use sticky notes and a timer to run a short retrospective for the group at large. Identify themes and discuss. Maximum ten minutes long.

The steps above described an in person event. To facilitate this online, an experienced facilitator is essential. 

### Next sessions

 Some considerations for the next  Bytesize Architecture Sessions

* Revisit the guest list.  Depending on availability and roles they might be more or less suitable. Consider,  are the participants able to contribute meaningfully? Does it help them in their role? 
* Have a strategy to make the outcomes of the sessions accessible to the wider organisation and consider a way to gather feedback
* Start with a short review of where you left the last time.  A quick overview is a great way to set the scene, then proceed with the goal
* If doing this online, have a template ready. Include images from the previous Bytesize Session
* Help participants see the effects of iteration, how they can point at something in the diagram and understand how it got to the current state. This is why the **Introspection** step at the end is so valuable.

The format of each of the Bytesize Architecture Sessions will follow the pattern of the infographic above. The goal should change according to how far people converge on the *System Context Diagram* and then, to the selected *Container Diagram*. 

It is possible that after working on the *Container Diagram*, the *System Context Diagram* needs to be updated.


## Results

### Outcomes

You might be wondering why should you go to all this trouble, after a few sessions the participants:

* Created together a model of what they think their system looks like. If there are unanswered questions or a non finished diagram, the type of questions and how the diagram is not complete will give everyone very good ideas about the type of knowledge that is missing.
* Shared what they know about their systems. 
* Heard different perspectives and, ideally, incorporated sections into the model they created together
* Learned C4 with hands on experience with a modelling technique, in this case C4
* Created a picture to help them jog their memory of this experience.  Doing the work collaboratively is like going on a holiday, and that the pictures we take while on holidays (unless you are a photographer) are a lot about being able to recall the experience.
* Are perfectly setup to continue iterating into deeper insights. For most significant work, a handful of Bytesize Architecture Sessions will help you complete a System context and container diagram. For each session, review the guest list (perhaps not everyone is suitable for the container diagram, for example)


With time, and assuming you adopt the practice , you will see the following effects:

* With support from leadership to sustain the practice, people know this is a time and place for advice when when making significant changes
* People learn that no-one knows everything, improved psychological safety 
* the designs become more nuanced, as People get better at modelling
* people want to learn more DDD 


### Common Anti‑Patterns 

* Staying on one discussion for too long. If participants are staying on a topic and not agreeing perhaps more context is needed. The impasse can be either addressed offline or on a follow up session where more participants have more context. Document the question or what needs to be investigated with precision and move on towards the goal. 
* Frustration because a diagram "not finished" and the timmer elapsed. This can be a little frustrating, and also it means we are constraining on time rather than completion. We are clearly indicating that the important thing is the learning, the understanding, not the artifact. The models we are creating are reflective of the systems, and those are never done either. Make sure you help attendees to see the progression. 
* Focusing on creating the perfect diagram, rather than understanding how the system works together. 
* Treating Bytesize Sessions as a meeting instead of a workshop. This can be a problem if there are people that dominate the conversation. The format of the workshop can help, but this might require coaching.
* Don't plan the goal of the next bytesize session. Make a decision about the goal as late as possible. Make sure you take feedback from recurrent attendees into account.



## Success Metrics

If you are trying out Bytesize Architecture Sessions or other techniques with similar goals. These can be useful metrics depending on your issues:

* A couple of weeks after a knowledge sharing session, ask participants to explain why a system or decision is the way it is. Not what it does, but **Why**
* New joiners capability to make decisions. Track when new joiners stop needing extra context or ask for validation on decisions. 
* Incident response and diagnostic speeds up. How long does it take to identify the root cause, and how many people need to be involved?
* Track the key-person risk. Identify top N people with the highest domain knowledge concentration in your organisation, over time, are those same top N people the ones with the highest domain knowledge concentration. Why?


## Conclusion

Kicking off a Design initiative generally brings a high level of uncertainty, Bytesize Sessions help by creating a safe space for design in deliberate manner in shorts and iterative bursts. 
Creating shared models help reduce risk and increase clarity. I have shared what works for me, I encourage you to try it and see how you it works for you. 
Maybe, certain aspect of this practice needs to be adapted for your context in some way. I would be very happy to hear about it.

I hope this has helped, if you are organising a session like this and have questions please do reach out. Next post will describe how to use Bytesize Architecture Sessions for [Define](https://github.com/ddd-crew/ddd-starter-modelling-process/blob/master/README.md#define). 
Until the next time.


[^CoMo]: Collaborative modelling is an approach experts, practitioners, and end-users, work together to create, refine, and validate models. Leveraging the diverse perspectives and expertise of the participants to enhance the model's accuracy, relevance, and usability. By involving a wide range of contributors,it fosters a deeper understanding of complex systems and promotes shared ownership of the outcomes.