---
date: 2015-12-06 20:13:00
layout: post
title: Even more Computation expressions
categories:
- programming
- fsharp
- For
- Yield
---

I am sorry for boring titles. After the last post I figured the For and Yield needed some extra clearing up.

This is post is not part of the [#FsAdvent](https://sergeytihon.wordpress.com/tag/fsadvent/), so if you are reading this you should go and check it out. Ready for some more computation expressions?

This post is the final part in a three part series about computation expressions

1.[Computaion expressions in practice](http://www.roundcrisis.com/2015/12/06/Computation-expressions-in-practice/) Introduces definition and parts of a computation expression, and a simple example.
2.[More computation expressions](http://www.roundcrisis.com/2015/12/06/more-computation-expressions/). Examples of a maybe monad and monoids with computation expressions

### How to draw a horse

In the previous post I left hanging exacly how things work and I thought that was a little unfair, a little like:

![drawahorse]({{ site.images }}/drawAHorse.jpg)


### Recap

So, the monoid computaton expression looked like this:

{% highlight FSharp%}

type MonoidBuilder ()=
  member this.Zero() = neutral

  member this.Combine(x, y) = addColour x y

  member x.For(sequence, body) =
      let combine a b = x.Combine(a, body b)
      let Z = x.Zero()
      Seq.fold combine Z sequence

  member x.Yield (a) = a

let monoid = new MonoidBuilder()

let monoidAdd xs= monoid {
     for x in xs do
       yield x
     }

{% endhighlight %}

#### Zero

Zero is one of those functions that are quite useful, it runs when

* Have an if expression with no else
* There is nothing else on the block

For example, the following

{% highlight FSharp%}

type ZeroBuilder ()=
  member this.Zero() =
    printfn "from Zero"

let zero = ZeroBuilder()

let test = zero{
	  printfn "not much going on"
	}

{% endhighlight %}


See you next time

Batmandrea


#### References

* [Functors, Applicatives, And Monads In Pictures](http://adit.io/posts/2013-04-17-functors,_applicatives,_and_monads_in_pictures.html)
* [Computation expression wikibooks](https://en.wikibooks.org/wiki/F_Sharp_Programming/Computation_Expressions)
* [Computation Expressions (F#) msdn](https://msdn.microsoft.com/en-us/library/dd233182.aspx)
* [Some Details on F# Computation Expressions - D Syme 2007](http://blogs.msdn.com/b/dsyme/archive/2007/09/22/some-details-on-f-computation-expressions-aka-monadic-or-workflow-syntax.aspx)
* [The computation expression series - F# for fun and profit](http://fsharpforfunandprofit.com/series/computation-expressions.html)
* [Why Do Monads Matter?](https://cdsmith.wordpress.com/2012/04/18/why-do-monads-matter/)
* [Where is the monad](http://www.quanttec.com/fparsec/users-guide/where-is-the-monad.html) A post on FParsec about why they moved away from a monadic aproach due to performance
* [The Road to Functional Programming in F# – From Imperative to Computation Expressions](http://richardminerich.com/2011/02/the-road-to-functional-programming-in-f-from-imperative-to-computation-expressions/)
* [FSharpx.Extras (github repo)](http://fsprojects.github.io/FSharpx.Extras/index.html)
* [The marvels of monads - Wes Dyer ](http://blogs.msdn.com/b/wesdyer/archive/2008/01/11/the-marvels-of-monads.aspx)
