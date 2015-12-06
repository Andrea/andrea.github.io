---
date: 2015-12-06 20:13:00
layout: post
title: More Computation expressions
categories:
- programming
- fsharp
- monoids
---

It is that time of the year, and [#FsAdvent](https://sergeytihon.wordpress.com/tag/fsadvent/) is now an event we all look forward during the happy season :D. Ready for some more computation expressions?

In the [previous post](http://www.roundcrisis.com/2015/12/06/Computation-expressions-in-practice/) I introduced a definition and parts of a computation expression, as well as some samples.

###



Another great example of computation expressions is error handling, how about


### Custom Operations

{% highlight FSharp%}

      type SimpleSequenceBuilder() =
          member __.For (source : seq<'a>, body : 'a -> seq<'b>) =
                 seq { for v in source do yield! body v }
          member __.Yield (item:'a) : seq<'a> = seq { yield item }
          [<CustomOperation("where")>]
          member __.Where (source : seq<'a>, f: 'a -> bool) : seq<'a> = Seq.filter f source        

      let myseq = SimpleSequenceBuilder()

{% endhighlight %}

and you can call this


{% highlight FSharp %}

    myseq {
        for i in 1 .. 10 do
        where (fun x -> x > 5)
        }

{% endhighlight %}

this translates to:

{% highlight FSharp %}

    let b = myseq
    b.Where(
      b.For([1..10], fun i ->
        b.Yield (i)),
      fun x -> x > 5)

{% endhighlight %}
