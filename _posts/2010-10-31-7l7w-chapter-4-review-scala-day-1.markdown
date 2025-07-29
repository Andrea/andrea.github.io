---
author: roundcrisis
comments: true
date: 2010-10-31 15:49:58+00:00
layout: single
classes: wide
slug: 7l7w-chapter-4-review-scala-day-1
title: 7L7W - Scala Day 1
wordpress_id: 711
---

In the Book Club, we are reading [7 Languages in 7 Weeks](http://www.pragprog.com/titles/btlang/seven-languages-in-seven-weeks) (for more info on the book club go to [Dublin Alt.Net mailing list](http://groups.google.com/group/dublinaltnet)) so far a really awesome book, Its helping me have a quick view of not only different languages, but also different programing paradigms. Which is really refreshing, but hard. The thing that I like the most about the book so far , is that you do much more than a hello world, but of course, you can learn in depth, however, the author makes a really good job of explaining what’s at the core of each language, sometimes, just trying to really grasp that is a tiny bit hard , when  it’s a paradigm you are unfamiliar with it, but the effort is well worth it.

Anyway, since I haven’t been able to the last two meet ups, I thought I’d do a second read of the Scala chapter and put together some notes. Please note I'm writing the notes as I read.

- Scala is a hybrid language (a mix of OO and functional)
- Hints that its a different kind of language
- Runs on the JVM, though given the state of Java, not sure that is any kind of insurance. Scala can use Java libraries natively, just like Iron* languages , can use .net libraries directly
- Statically typed
- type inference (like c#? –> review)
- functional concepts, like c#? it would be awesome if it added some native support for immutable types
- Support immutable types, but its got some modifier ( need to check this out more in depth)
- actors

Scala is a general purpose language, interesting that it seems to fit well many scenarios because of this OO, Functional mix
Type inference seems to be not so strong
Principles of functional programming that apply to Scala:
- programs are made of functions
- functions return a value
- given the same input, a function will return the same output
- side effect free

val is immutable var not .... Likes

There is a full page on the book dedicated to somewhat clarifying strong vs weak and static vs dynamic  languages. I mostly agree with his points there.

My first impression when seeing the language was that it reminded me more to python than to java, maybe it was **def** .



	
  * Visibility of methods, functions. Public is default

	
  * Support for tuples and ranges . In purely functional languages, tuples are used as objects. You can do multi value assignment with tuples

	
  * Constructors. I like Scala’s  syntax and default

	
  * Object instances are interesting, at first I was thinking they were like static classes in C#, but apparently not quite. As far as I understand, an object declaration in Scala is basically a singleton instance of a class definition.  However, in C# a static class is a class that can be accessed and used, without creating an instance. That makes me think that there is a cost associated with the instantiation, but I cant see any other difference. (comments on this would be appreciated)

	
  * traits. Like an interface and an implementation all in one, generally focusing on a single concern, well that’s what the book say, however I can’t see here how you do to declare a trait separetly


As Part of the exercise of Day 1 you need to find a comparison between Java and Scala(I found [this](http://blog.lostlake.org/index.php?/archives/26-5-Things-a-Java-developer-needs-to-know-about-Scala.html)), one of the interesting things I learned while checking that out is that XML is supported natively, I also liked the point on moving to a more functional style of programming slowly, but with a nicer syntax.
