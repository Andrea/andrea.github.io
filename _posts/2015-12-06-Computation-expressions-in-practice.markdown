---
date: 2015-02-22 19:44:00
layout: post
title: Computation expressions and microphones
categories:
- computation expressions
- fsharp
- monoids

---

It is that time of the year, and [#FsAdvent](https://sergeytihon.wordpress.com/tag/fsadvent/) is now an event we all look forward during the happy season :D. My contribution to it is this write up about computation expressions.


### Why?
I guess it is kind of hard to learn something if you don't know what to use it for.

Some well known usages of computation expressions are asynchronous programming or creating DSLs.
They allow you to determine the semantics of your code, in short, you can decide how your code gets
executed.

Having a computation do some of the heavy lifting behind the scenes can
dramatically reduce redundant code.


### You were saying about practice?

Below is an example of a computation expression builder. Which is a "normal" F# type that has some methods that the F# compiler will look for. The compiler recognizes a builder because it has certain functions with well defined names (such as Bind, Return, For, etc), more on this later.
