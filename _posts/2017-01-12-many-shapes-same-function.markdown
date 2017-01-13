---
date: 2017-01-12 23:13:00
layout: post
title: Many shapes and the same function
categories:
- programming
- scala
- foldleft
- point-free
---

I was playing around with a small function in Scala and found it kind of interesting that you can express the same thing in
different ways.
We are writting a function that will fold over a string an accumulate on running `parensToFloor` a function that looks
like:

```
def parensToFloor(c:Char): Int = ???
```

The most common way to write this function would be:

```
def myFn1(s:String) : Int = {
	s.foldLeft(0)((x,y) => x + parensToFloor(y))
}
```

What would it look like [point free](https://en.wikipedia.org/wiki/Tacit_programming)? 

I arrived to a few options that didn't work :

```
def myFnx(s:String) : Int = {
    s foldLeft 0 { _ + parensToFloor(_)}
//>error: Int(0) does not take parameters
//              s foldLeft 0 { _ + parensToFloor(_)}
//                          ^
}
```
this made sense to me but the following one...mmm I imagine the compiler sees that since foldLeft is curried then it makes sense but what does the compiler want?


```
def myFnx(s:String) : Int = {
    s foldLeft 0 apply { (x,y) =>_ + parensToFloor(_)}
// >error: missing arguments for method foldLeft in trait IndexedSeqOptimized;
//follow this method with `_' if you want to treat it as a partially applied function
//             s foldLeft 0 apply { (x,y) =>_ + parensToFloor(_)}
//              ^
}
```

so thinking about that and how to curry, I started trying to add parens around and see what happens and
this worked:

```
    (s foldLeft 0) { _ + parensToFloor(_)}
```

Something that worked but it wasn't what I was looking for (it needed a change to the definition of `parensToFloor`):

```Scala

def parensToFloor(accumulated:Int, c:Char):Int = ???

//... more stuff.

def myFnx(s:String) : Int = {
// first the non working version same error as before
s foldLeft 0 parensToFloor

// than later evolved to because apply was missing
(s foldLeft 0) { parensToFloor }

```
then since we are here, might as well go and try and see what it looks like with operators (from a coworker):

```
(0 /: s) { _ + parensToFloor(_) }
```

An interesting thing is that the usage of parens and braces is something I still find confusing in time in Scala. 
The source of my confusion is not totally unfounded, in the [docs]() we can see that: 

* ( )        // Delimit expressions and parameters
* { }        // Delimit blocks

however [here](https://www.scala-lang.org/files/archive/spec/2.11/06-expressions.html) we see that blocks can also be expressions...


I'll have to leave this here. More to follow...

