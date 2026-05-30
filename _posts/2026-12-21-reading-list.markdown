---
date: 2026-12-21 00:12:00
layout: single
title: Interesting learning resources - February 2026
categories:
- software architecture
- iteration zero
- ddd
excerpt: "These resources span from practical case studies in team scaling to theoretical frameworks for understanding programming languages, unified by a common thread: how we structure our thinking to solve hard problems. Whether examining ProTime's journey from feature teams to domain-owned teams, exploring different approaches to teaching programming concepts, or critically evaluating the models that shape our decision-making, each resource helps navigating the experience of building software.."
image: "/images/2025/models-rwb.png"
tags: [case study, event storming, software architecture, denotational understanding, operational understanding]
---


### What Kind of Programming is Natural Language Programming?

https://dsyme.net/2025/09/02/what-kind-of-programming-is-natural-language-programming/


### Domain, Subdomain, Bounded Context, Problem/Solution Space in DDD: Clearly Defined by Nick Tune

[link](https://medium.com/nick-tune-tech-strategy-blog/domains-subdomain-problem-solution-space-in-ddd-clearly-defined-e0b49c7b586c)

In this post from 2020 Nick beautifully explains key DDD concepts in easy to understand ways


![alt text]({{site.images}}/2025/glad-we-all-agree-1.png) 
Credit: [Jeff Patton](https://jpattonassociates.com/glad-we-all-agree-2/)


### No, Your Domains and Bounded Contexts Don’t Map 1 on 1 - By Mathias Verraes
Bounded Contexts are a design choice to suit engineering needs



https://verraes.net/2025/08/domain-and-bounded-contexts-dont-map-one-on-one/



## LIV BOEREE - a non-zero hero by James

[link](https://nonzerosum.games/nonzeroherolivboeree.html)

## The Early History of F#

[pdf](https://github.com/dsyme/dsyme-presentations/blob/master/2021-06-21-hopl/the-early-history-of-fsharp-given.pdf)
This paper presents Don Syme's perspective on the history of F#, structured around six key narratives. Syme describes how F# emerged from the collision between strongly-typed functional programming traditions and the object-oriented tidal wave of the 1980s-90s, particularly within Microsoft's ecosystem. He explains how F# was born from an "obsessive compulsion" to ensure functional programming remained viable in the 2000s, starting with OCaml's core but adapting it to interoperate with .NET's industrial virtual machine and ecosystem.
The presentation highlights how F# successfully resolved several contradictions within the functional programming community by introducing innovative features like functional objects, active patterns, and computation expressions. These additions allowed F# to maintain its functional core while becoming practical for real-world development, ultimately influencing many modern programming languages including C#, Scala, TypeScript, and others. Syme emphasizes that the "golden thread" of strongly-typed functional programming - exemplified by simple constructs like let f x = (x, x) - has remained constant from the 1970s through today and will continue to appeal to programmers in the future.


### Code Review Can Be Better by matklad


[link](https://tigerbeetle.com/blog/2025-08-04-code-review-can-be-better/)

This is a common pattern most of us use when reviewing code

> When I review code, I like to pull the source branch locally. Then I soft-reset the code to mere base, so that the code looks as if it was written by me. Then I fire up magit, which allows me to effectively navigate both through the diff, and through the actual code. And I even use git staging area to mark files I’ve already reviewed
>...
> Alas, when I want to actually leave feedback on the PR, I have to open the browser, navigate to the relevant line in the diff, and (after waiting for several HTTP round-trips) type my suggestion into a text area. 



### Amazon's ADR process
[link](https://docs.aws.amazon.com/prescriptive-guidance/latest/architectural-decision-records/adr-process.html)

## To read

* [The Three Kinds of Organizational Power](https://jacobian.org/2021/mar/15/organizational-power/) by Jacob Kaplan-Moss. I did read this, but given the work I'm doing I need to dive deeper on this, thanks Anja Kunkel for sharing this write up with me.

* [Navigating Firestorms: The Imperative of Conflict-Intelligent Leadership in a Turbulent World Open Access](https://direct.mit.edu/ngtn/article/40/1-2/5/123561/Navigating-Firestorms-The-Imperative-of-Conflict)

* https://www.caitlinsteele.com/open-pit-programming-silicon-valleys-industrial-extraction-of-human-potential-part-i-2/



Practice is where we truly learn, and so with these case of results does Residuality give you, but also how to practically implement it within the context of practitioners that prefer to work collaboratively. 
Residuality, as far as we understood at the beginning of the journey, is all about giving you an architecture that can withstand the stressors that you've analyse. Ideally, this generates residues that enable you to address multiple stressors with one residue, or with the outcomes of some residues, right? So you have a residual architecture at the end. What does DDD promise then? Residuality tells you that the software itself is not complex but complicated. DDD says that we have complexity in software systems, so that's at least one question that we want to try to answer. Another question that is really— so there's, there's what are we trying to learn. A) How do we integrate Residuality in the context of our practices? Like, concretely. B) What does it actually give you? As in, you do Residuality in some way and you do this exercise, what do you get out of it? Is it useful? Why? How is it useful? How long does it take? Can you easily quantify the effort? Who is needed? Who should participate in the activities related to Residuality? Why? Who's excluded? Also why? And finally, one of the kind of two key questions that we have is: what do you actually do with the residues? Now, as far as we understand, when you finish doing the, the residuality exercise, you end up with this residual architecture, and that means that you have a bunch of residues that you could implement. However, when it comes to— well, you can't do all of these things generally, so in theory you have a bunch of residues and there will be quite a delta between your current or /naive architecture and your residual architecture. How and why, what do you do with it? How do companies actually— how do organisations really use the outcome of this exercise? What does that mean? And that's pretty much what I've been doing.