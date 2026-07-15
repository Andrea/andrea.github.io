---
date: 2027-07-09 00:12:00
last_modified_at:  2026-07-09 00:12:00
layout: single
title: Residuality Case Studies - Part 1 Introduction
categories:
- software architecture
- architectural decision
- residuality
- randomness
- residues
- attractors
- stressors
excerpt: "First of a series about Residuality:Real World Comparative Case Studies"
tags: [ software architecture, residuality, case-study, randomness]
---


The key idea behind Residuality is that a random simulation of stress produces an architecture more likely to survive scenarios that were never anticipated. Although there are many papers, a book and multiple videos about Residuality, there is not a lot about what happens when you use it in practice. This is a write up about our experience using Residuality in two organisations: Contextive, a solopreneur project that grew out of an open source project and Lexer, a 17 years old Customer Data Platform organisation that was looking to revitalise their systems while facing seismic changes in the industry.

A little background about the people that worked on the case study: Chris and I are both independent consultants and we collaborated working with clients in the past. We found common ground in collaborative modelling and Domain-Driven Design.   
For some time we've been discussing,and learning Residuality. We’ve both read the book [Residues: Time, Change, and Uncertainty in Software Architecture](https://leanpub.com/residuality), watched videos online and Chris attended the Residuality Training Workshop at DDD Europe 2025\.   
The obvious next step was to use Residuality. The problem was how to find suitably real problems.

Early on 2026, an opportunity materialised with a new client, they needed to evaluate their system to see how to improve their architecture so that it would be more able to withstand current and future problems, in other words, they were looking to update their system to have more adaptive capacity[^1] . The challenge?  A 17 year old project with big needs to modernise in effective ways, their rate of change was too slow and something needed to be done.  

We thought that if we were to practice Residuality and document the process to share what we learned, then we would be more deliberate on the practice and we would take more care in collecting what we learned  
We have since presented what we learned at DDD Europe in June 2026 and Convex, there are more scheduled presentations booked.

{% include figure popup=true image_path="/images/2026/residuality-ddd-eu.png" alt="DDD EU 2026" caption="At DDD Europe 2026." %}

## What is Residuality?

For an in-depth description of Residuality, the best place is Barry O’Reilly’s book on the subject, [Residues: Time, Change, and Uncertainty in Software Architecture](https://leanpub.com/residuality).

The key idea behind Residuality is that a random simulation of stress produces an architecture more likely to survive scenarios that were never anticipated. Organisations want to build systems that can survive randomness because unlikely events that have disproportionate side effects, known as Black Swan events, can break organisations. In Residuality, instead of starting to design your system thinking in terms of use cases, data or microservices you start by asking, when something goes wrong, what is left? residues.

Using Residuality gives the people involved in designing software systems direct links between non-functional requirements and potential changes to a system.

>”Residuality is defined here as the property of having residues when exposed to stress. That is, when exposed to a certain stressor, some part of the system will remain. We call this remaining part of the system a residue, which is expressed as a collection or set of components, infrastructures, people, and information flows – a flow being the transfer of data from one actor in a system to another”*  
*(Source: An Introduction to Residuality Theory: Software Design Heuristics for Complex Systems \- Barry M. O’Reilly)* 

To start with, let's look at a more concrete, yet simple example.  Say that there is a system that has three components, like in the image below; this is the system as we understand it now. In Residuality we call that naive architecture. 


{% include figure popup=true image_path="/images/2026/residuality-1.png" alt="Residuality - Naive architecture" caption="Three components representing a Naive Architecture." %}

Then consider a change that happens in the environment of the system, it can be a new requirement, a new market, customer feedback, government regulations, etc. This is called a **stressor**. We are representing the stressor in the picture below with a yellow lighting bolt.

{% include figure popup=true image_path="/images/2026/residuality-2.png" alt="Residuality - Stressor" caption="Naive Architecture with Stressor." %}

Can the system survive this stressor? If not, then we would need to make some changes to the naive architecture, those changes are called **deltas.**

{% include figure popup=true image_path="/images/2026/residuality-3.png" alt="Residuality - Delta" caption="Naive Architecture with Stressor and Delta." %}

In real systems, you generally have more than one problem, conversely you consider many stressors interacting with the naive architecture and analyse them one by one. As you do that, you come up with distinct deltas. At this point, an interesting thing happens, you end up with the same delta for different stressors. The collection of all the distinct deltas is the **residual architecture**. 

{% include figure popup=true image_path="/images/2026/residuality-5.png" alt="Residual architecture" caption="Residual architecture view with stressors and common deltas." %}

These concepts are the essential Residuality concepts you need to follow along so far, there are more and they will be introduced as they are needed.

At the heart of Residuality Theory is the idea that software is ordered enough or at worse, complicated but forced to live within a complex environment. Since complexity can’t be predicted, then the best option is to use complexity-based tools to manage this.When thinking of stressors, the best quality for a collection of stressors is that they are random.   
Randomness in this case will help with designing a system that can survive some sets of random stressors, as you iterate on the process of using Residuality you will find that random stressors can also help you validate your naive architecture against your new residual architecture.

Saying that a good property of a collection of stressors is that they are random might intuitively feel like a mistake (or at minimum a disadvantage), this is not the case, for starters it’s a great way to explore the problem space with concrete, specific questions without having to restrict yourself on how likely it is that those scenarios are going to happen. It can also help with reducing bias by looking at all ways a system can not be ok, not just the scenarios you/someone considers most important.  
One important thing to consider is that when you arrive at a Residual architecture you are not saying that you will build exactly this right now, but it will give you the understanding of what you should build and maybe you can do just enough implementation (ie can guide boundaries and contracts or where components should split)

## Why Case Studies, why now?

There are two reasons behind this work: the organisation's reasons for wanting it, and our own reasons for writing it up.

**The organisation's perspective**

Lexer was facing seismic change in its industry and needed swift improvements to a system that had grown complicated over seventeen years. They wanted their next architecture to withstand random, unanticipated stress rather than the specific problems they already knew about. When we described what Residuality promised, it matched what they were looking for closely enough that the decision to try it was easy.

**Our perspective**

When we started, we had a set of open questions about Residuality in practice, and those questions are what shaped the case studies. The questions:

* Does it work?  
* Can we use collaborative techniques with Residuality?  
* Who and how do we find stressors, attractors and how to get good Residues?  
* What makes a residue good? Why?  
* How useful is the random simulation in practice?   
* What do you do with the Residual Architecture? How do you use the outcomes? It’s unlikely that you can immediately implement all of the residues at once.    
* When analysing ways to stress the system, and how the system reacts, many questions about the business strategy are bound to arise - What if there are no answers to these?  
* Can / should average developers use this? How can you find Residuality useful if you didn’t “feel the pain”?

These questions drove how we went about practising Residuality. 

Domain-Driven design has had a central role in both Chris’ and my software design and architecture practices. Our paths are not the same but we ended up in similar places. We understand and value focusing on a rich domain and having a series of heuristics, patterns and vocabulary to describe its components. We also value collaborative modelling techniques as they have consistently delivered higher value faster. 

A lot of these ideas seem to be in contradiction with Residuality Theory. Ultimately we wanted to know how and if our way of thinking and working would change. 

### Two case studies? 

This write up is about two systems. One is [Contextive](), a ‘solopreneur’ startup, currently in private beta and building on the foundations of an open source project. All the context for this system lives with one person, and that person is Chris\! Meaning we have full access to any information we could need.   
We thought we should start with Contextive so that we could learn the practice of Residuality in a simpler setting and also wanted to use it as a Baseline. It allowed us to focus on the raw process and mechanics of Residuality. And since I didn’t know about Contextive’s design and architecture, this would mean that we would start uncovering some assumptions. 

Then there is [Lexer](), a customer data platform in Australia.  It was founded over 15 years ago and, over the years they had a few different areas of focus as they worked towards product-market fit. At the time we engaged them they were looking for clarity on the current state and finding a way forward, they were also looking to inform significant organisational changes.  
And then when working on Lexer, the plan was to have a better idea of what to expect from Residuality and deal with the realities of a larger system and collaborative techniques.

## Who are we?

Philosophical jokes aside, perhaps the more useful question is why us. The short answer is we thought our lens as Domain-Driven Design practitioners might be valuable. Also the fact that this work collects the perspectives of two systems, might make this more valuable.

Chris is an experienced technology leader, start-up founder, director, systems architect & full-stack software/cloud engineer.He leads with compassion and empathy, designs with creativity and innovation, and builds systems with rigour and discipline.
He loves building and working with technology in complex domains but always ensure he and those around him stay connected to their purpose and the people in their sphere, be they customers or colleagues.

In turn I've spent a quarter of a century building systems across demanding domains such as financial platforms, video streaming, ecommerce, and video games. That breadth means I've seen a lot of approaches succeed, and more importantly, I've felt the consequences when they don't. Exploring type-driven design through F\# and Scala helped me grow as a programmer and hone my skills as a modeller, by leaning on the compiler to be more declarative about the properties of the systems I’ve built.  
Returning to Domain-Driven Design afterwards was a progression. I came back with a sharper understanding of what DDD offers that pure type modelling can't, particularly around collaboration and the discipline of deeply learning the domain you're building for.  
The  combination of an extensive technical foundation, experience with DDD across different phases of my career, and a focus on how collaboration and domains shape systems is why I feel I can bring a hopefully useful case study or experience report of using Residuality. 



## What's next

Now that we have set some ground work, we can move on to the next steps, covering the items on this mind map

{% include figure popup=true image_path="/images/2026/m-residuality.png" alt="What we want to cover in this series" caption="What we want to cover in this series." %}

<!-- 
graph LR
    Residuality["Residuality"]

    subgraph KC["Key Concepts"]
        Stressors["Stressors"]
        Criticality["Criticality"]
        Attractors["Attractors"]
        AdaptiveCapacity["Adaptive Capacity"]
        Residues["Residues"]
        Deltas1["Deltas"]
    end

    subgraph AC["Activities"]
        StressorAnalysis1["Stressor Analysis"]
        IncidenceMatrix1["Incidence Matrix"]
        FlowAnalysis["Flow Analysis"]
        ResidualIndex["Residual Index"]
    end

    subgraph CS["Case Studies"]
        FutureQuestions["Future Questions"]
        subgraph CX["Contextive"]
            CompanyContextC["Company Context"]
            NaiveArchitectureC["Naive Architecture"]
            StressorAnalysisC["Stressor Analysis"]
            BusinessImpactC["Business Impact"]
            DeltasC["Deltas"]
            IncidenceMatrixC["Incidence Matrix"]
            ResultsC["Results"]
        end
        subgraph LX["Lexer"]
            CompanyContextL["Company Context"]
            NaiveArchitectureL["Naive Architecture"]
            StressorAnalysisL["Stressor Analysis"]
            BusinessImpactL["Business Impact"]
            DeltasL["Deltas"]
            IncidenceMatrixL["Incidence Matrix"]
            ResultsL["Results"]
        end
        CollaborativeActivities["Collaborative Activities"] -.-> CX
        CollaborativeActivities -.-> LX
        LessonsLearned["Lessons Learned"] -.-> CX
        LessonsLearned -.-> LX
    end

    Residuality --> KC
    Residuality --> AC
    Residuality --> CS

    classDef center fill:#f0f0f0,stroke:#666,stroke-width:3px,font-weight:bold
    classDef kcNode fill:#cfe8f3,stroke:#7fb3d5
    classDef acNode fill:#d0f0d0,stroke:#82c48a
    classDef csNode fill:#fde2c8,stroke:#f0b27a
    classDef cxNode fill:#fdf2b3,stroke:#e8d580
    classDef lxNode fill:#e5d4f0,stroke:#c39bd3

    style KC fill:#eaf6fb,stroke:#7fb3d5,stroke-width:2px
    style AC fill:#eafaea,stroke:#82c48a,stroke-width:2px
    style CS fill:#fef6ea,stroke:#f0b27a,stroke-width:2px
    style CX fill:#fefbe0,stroke:#e8d580,stroke-width:2px
    style LX fill:#f5edfa,stroke:#c39bd3,stroke-width:2px

    class Residuality center
    class Stressors,Criticality,Attractors,AdaptiveCapacity,Residues,Deltas1 kcNode
    class StressorAnalysis1,IncidenceMatrix1,FlowAnalysis,ResidualIndex acNode
    class FutureQuestions,CollaborativeActivities,LessonsLearned csNode
    class CompanyContextC,DeltasC,StressorAnalysisC,IncidenceMatrixC,NaiveArchitectureC,BusinessImpactC,ResultsC cxNode
    class CompanyContextL,DeltasL,StressorAnalysisL,IncidenceMatrixL,NaiveArchitectureL,BusinessImpactL,ResultsL lxNode  -->

 

[^1]:  Adaptive Capacity: is the ability of an organisation to push the system back to stability within a certain range of desirable attractors–defined by safety standards