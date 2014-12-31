---
date: 2014-12-31 11:44:00
layout: post
title: What is a type system
categories:
- programming 
- development
---

Curiosity killed the cat, good thing cats have 9 lives...


I don't know you, but after using a few programming languages I have too many questions about type systems, some that come to mind

* What is a type system? 
* Do we need one? 
* When do we not need one?
* What is the relation between type systems and property testing? or is there one?
* Why is category theory so important in advances type systems? (I have intuition but no answers yet) 
* Are there pure definitions for the different types of types systems?

Probably some of those questions make no sense, at least until I understand the answers.

Thankfully, I was not alone in asking myself [this question](http://lambda-the-ultimate.org/node/412). 

If you are looking for strong vs weak and static vs dynamic articles I found a this one (there are many more)
* [What To Know Before Debating Type Systems](https://cdsmith.wordpress.com/2011/01/09/an-old-article-i-wrote/)


### What is a type system?

Like most interesting things, this simple question yields multiple answers

* [**Wikipedia**](http://en.wikipedia.org/wiki/Type_system#cite_note-FOOTNOTECardelli20041-2) In programming languages, a type system is a collection of rules that assign a property called a type to the various construct—​such as variables, expressions, functions or modules—​that a computer program is composed of.[1] The main purpose of a type system is to reduce bugs in computer programs[2] by defining interfaces between different parts of a computer program, and then checking that the parts have been connected in a consistent way. This checking can happen statically (at compile time), dynamically (at run time), or it can happen as a combination of static and dynamic checking. Type systems have other purposes as well, such as enabling certain compiler optimizations, allowing for multiple dispatch, providing a form of documentation, etc.

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

Then I found this **gem** that really got me thinking

[@mrb_bk](http://twitter.com/mrb_bk) wondered [What is a type system for](http://michaelrbernste.in/2014/02/17/what-is-a-type-system-for.html) This is totally worth the read. The TL;DR

 
"The most basic property of this type system or any other is safety (also called soundness): well-typed terms do not 'go wrong.'"

What does "go wrong" means in this context?

"...it means reaching a 'stuck state' that is not designated as a final value but where the evaluation rules do not tell us what to do next."


"What we want to know, then, is that well-typed terms do not get stuck. We show this in two steps, commonly known as the progress and preservation theorems."

"Safety = Progress + Preservation"

That is where I am going to leave this for today, plenty to think about. 

### Worth Reading

As a novice in this area I found The paper by [Luca Cardelli][1] is a good read .

Also [this pdf](http://www.cis.upenn.edu/~bcpierce/papers/tng-lics2003-slides.pdf) by [Benjamin C. Pierce](http://www.cis.upenn.edu/~bcpierce/) contains an overview of the available literature up until year 2003. 


### Some related stuff

* [Is C# a strongly typed or a weakly typed language? Eric Lipert's blog](http://blogs.msdn.com/b/ericlippert/archive/2012/10/15/is-c-a-strongly-typed-or-a-weakly-typed-language.aspx)
* [Types systems- The good, the bad and the ugly](https://www.youtube.com/watch?v=SWTWkYbcWU0) A highly controversial talk about type systems that I enjoyed greatly, I hope conferences keep bringing talks that people have string feelings about. 

### References

[1](http://www.cis.upenn.edu/~bcpierce/tapl/)
[2](http://lucacardelli.name/Papers/TypeSystems.pdf)
[Type Systems for Programming Languages](http://www.cs.cmu.edu/~rwh/misc/tspl.pdf) It's a scary one 
[Practical Foundations for Programming Languages](http://www.cs.cmu.edu/~rwh/plbook/book.pdf)


Happy new year!! 