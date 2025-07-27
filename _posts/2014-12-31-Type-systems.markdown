---
date: 2014-12-31 11:44:00
layout: single
classes: wide
title: What is a type system
categories:
- programming 
- development
---

Curiosity killed the cat, good thing cats have 9 lives...


I don't know you, but after using a few programming languages I have too many questions about type systems, some that come to mind:

* What is a type system? 
* What is a type?
* Do we need a type system? 
* When do we not need one?
* What is the relation between type systems and property testing? or is there one?
* Why is category theory so important in advanced type systems? (I have intuition but no concrete answers yet) 
* Are there pure definitions and implementations for the different types of types systems?

Probably some of those questions make no sense, at least, until I understand the answers.

Thankfully, I was not alone in asking myself questions. For example [this question](http://lambda-the-ultimate.org/node/412) seems to spiral into no concrete answers. 

If you are looking for a post about  Strong vs Weak typing and Static vs dynamic typing articles I found a this one (there are many more)

* [What To Know Before Debating Type Systems](https://cdsmith.wordpress.com/2011/01/09/an-old-article-i-wrote/)


Anyway I am starting off with the first question.

### What is a type system? 

According to

* [**Wikipedia**](http://en.wikipedia.org/wiki/Type_system#cite_note-FOOTNOTECardelli20041-2) In programming languages, a type system is a collection of rules that assign a property called a type to the various construct—​such as variables, expressions, functions or modules—​that a computer program is composed of.[1](http://www.cis.upenn.edu/~bcpierce/tapl/) The main purpose of a type system is to reduce bugs in computer programs[2](http://lucacardelli.name/Papers/TypeSystems.pdf) by defining interfaces between different parts of a computer program, and then checking that the parts have been connected in a consistent way. This checking can happen statically (at compile time), dynamically (at run time), or it can happen as a combination of static and dynamic checking. Type systems have other purposes as well, such as enabling certain compiler optimizations, allowing for multiple dispatch, providing a form of documentation, etc.

Ok, a bit generic, but helpful:

* There are rules 
* There are constructs
* A program is composed by the aforementioned constructs
* type systems help prevent errors


Other definitions I found online are as simple as:

* A type is a label (can't remember who said this)
* "...A type is simply a name for a collection of related values just like a food group, it's a name for a collection of foods with related properties
and a type is a name for a collection of values that we code with
that have similar properties" From Erik Meijer latest course on [functional programming (Lecture 2 part 1)](https://courses.edx.org/courses/DelftX/FP101x/3T2014/info)

* [**Benjamin C Pierce from TAPL**](http://www.cis.upenn.edu/~bcpierce/tapl/index.html) A type system is a tractable syntactic method for proving the absence of certain program behaviours by classifying phrases according to the kinds of values they compute. 

This is a more helpful

* Tractable and syntactic **method**
* **absence of behaviours** (perhaps runtime errors)
* Classification of phrases according to kind of values

As I was thinking a little about this I found this **gem** of a post:

[@mrb_bk](http://twitter.com/mrb_bk) wondered [What is a type system for](http://michaelrbernste.in/2014/02/17/what-is-a-type-system-for.html) This is totally worth the read. The post is based on studying TAPL. The TL;DR of the post goes like:
 
    "The most basic property of this type system or any other is safety (also
    called soundness): well-typed terms do not 'go wrong.'"

What does "go wrong" means in this context?

    "...it means reaching a 'stuck state' that is not designated as a 
    final value but where the evaluation rules do not tell us what to do next."

In this context thinking of getting stuck as runtime errors is acceptable.

    "What we want to know, then, is that well-typed terms do not get stuck. We 
    show this in two steps, commonly known as the progress and preservation 
    theorems."

The theorem definition and explanation is in the post, but I had to stop and thing about:

    "Safety = Progress + Preservation"

That is where I am going to leave this for today. 

### Worth Reading

As a novice in this area I found The paper by [Luca Cardelli][1] is a good read .

Also [this pdf](http://www.cis.upenn.edu/~bcpierce/papers/tng-lics2003-slides.pdf) by [Benjamin C. Pierce](http://www.cis.upenn.edu/~bcpierce/) contains an overview of the available literature up until year 2003. 

### Some other related reads


* [Is C# a strongly typed or a weakly typed language? Eric Lipert's blog](http://blogs.msdn.com/b/ericlippert/archive/2012/10/15/is-c-a-strongly-typed-or-a-weakly-typed-language.aspx)
* [Types systems- The good, the bad and the ugly](https://www.youtube.com/watch?v=SWTWkYbcWU0) A highly controversial talk about type systems that I enjoyed greatly, I hope conferences keep bringing talks that people have string feelings about. 

### References


* [Type Systems for Programming Languages](http://www.cs.cmu.edu/~rwh/misc/tspl.pdf) It's a scary one 
* [Practical Foundations for Programming Languages](http://www.cs.cmu.edu/~rwh/plbook/book.pdf)


## Feedback other resources?

Do you know of other type system resources I should look into? 
Do you know of any other links I should look into?
Any comments? Let me know

# Happy new year!! 