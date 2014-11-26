---
date: 2014-11-24 11:44:00
layout: post
title: CodeMesh braindump, notes
categories:
- programming 
- development
- Duality
- Fsharp
- AI
- Idris
- Conferences
---

I took some notes during CodeMesh a few weeks ago, and here they are. There are a few good talks that I couldn't attend that are totally worth it, check them out when their videos become available.

Last year, CodeMesh showed me a lot of what I felt I was missing. This year was also quite amazing, the talks and people made it totally worth it. These are some notes I took during the talks, not sure they would help anyone, you never know.


## QuickCheck tutorial

* shrinking, find hints in shrinks. Mostly deterministic to help you find  hints fast
* when comparing you need to find the simplest thing to compare to
* Stats help you check if the calls make sense
* There are pre and post conditions 
* generally you discover many bugs with one property
* Race condition -> makes calls in orders humans wouldnt do it because it doesnt make sense to us
* quick check CI

## Idris tutorial

Idris is a general purpose pure functional programming language with dependent types. Dependent types allow types to be predicated on values, meaning that some aspects of a program’s behaviour can be specified precisely in the type. It is compiled, with eager evaluation. Its features are influenced by Haskell and ML.

* pacman ready
* Vim or Emacs
* think of proofs

It is hard to explain in these lines what the experience was like. Writing Idris was more like doing Maths or Algebra that it was to write code, I wold say that is something you want in some cases.
You can find windows binaries [here]()
It felt like the code needed to balance itself. The editor environment was a huge help as it helped reduce statements.

## Keynote: Jessica Kerr and Dan North

Great keynote that made us all think about the systems we write, about all the concerns we need to be aware of.

* estimation by range , the bigger the range the bigger the unknowns
* introduce research as part of all sprints


Not all of us build software with a narrow specific focus

## Gamedev-grade Debugging - Leszek Godlewski

This session felt like therapy, all the crazy bugs that are gamedev specific, exposed

* Three types of bugs: temporal, graphical, content.
* sometimes terrible hakcs,
* Domain specific debbugers


He also recommended and missed Valgrind. The Valgrind tool suite provides a number of debugging and profiling tools that help you make your programs faster and more correct. The most popular of these tools is called Memcheck. It can detect many memory-related errors that are common in C and C++ programs and that can lead to crashes and unpredictable behaviour.

## Yan Cui, Neo 4 J

Very cool tool about the complexity of their game and economy and how they are suing this graph database to curb it.
I am not sure we can/should use this because we don't have the same scaling issues, but great to see none the less.
Awesome style of presentation too. 


## Behaving in the 21st Century - AI Productivity through Tooling - Emil Johansen

[Slides](http://www.codemesh.io/static/upload/media/1415724623396237behavinginthe21stcentury.pdf)

Emil presented a tool he built for Behaviour Trees, the tool generates behaviour code. I really liked the demo he showeed
My main take on it was that I am glad to see tools like this 

 * BTs as iterative tools
 * code generation
 * A different workflow (to ours in Duality)


## The tools that shape us

I'm going to do this the other way around and tell you how was it for me to prepare this talk, because ...coverage and correctness (and as a test).

The talk was about highlighting the importance of tools, and how important it is for us to make sure we provide good tools for others to work with. 
As developers our tools are also important:

 * Languages
 * Ecosystem
 * Comunities
 
Tools model the way we think, it might be worth trying out something totally different just to see what though process it bring us.

## Alex Champandard

Talked about AI on the GPU. Great talk and presentation. Not only content but style (impecable)

* OpenCL and what we can do
* can do A*
* seaparate GPU for processing and rendering
* Sycl 
* A lot of cool ideas perhaps not ready for production yet.


## Ramsey and Tims

This is the second time i see this presentation however, it was totally different than the last time I saw it

* Simplify game development by using a more terse language (I can relate :) )
* [Arcadia](https://github.com/arcadia-unity/Arcadia), using CLR implementation of Clojure on top of Unity.
* REPL as a way to game design
* extra bonus points because they showed a game with cats!


## Keynote: Chad Fowler

* the theme of the keynote was tiny
* Big tends to fail
* Some of his experince with failure
* where are we now.

Left me thinking 

## Typed Clojure in Practice - Ambrose Bonnaire-Sergeant

I was really curious about this because I imagined it would be hard to add typing to a lisp, as a noob, that only did the equivalent of a hello world in clojure.
I have to add, Ambrose passion and enthusiasm for this project is contagious 

## Functional Patterns in Domain Driven Design applied to Financial Models - Debasish Ghosh
 
* Modelling in financial
* Introduced some algebra at a nice pace, logically.
* Financial with cool examples

## Naming things - Ian Barber

A lot of stuff to think, but didn't take notes, worth a watch when it comes online.

## Gluing Things Together with Haskell - Neil Mitchell

Really liked checking out Shake and Bake, and how people are deplying things in Haskell. Great presenter too.

## Summary

As you see, my notes got sparse towards the end, but ... I'll learn to take better notes hopefully. Again, one of the most interesting things about conferences is that, you get to talk to a lot of people thinking similar or totally diffrent thoughts to yours about similar topics. Left inspired and looking forward to next year!
