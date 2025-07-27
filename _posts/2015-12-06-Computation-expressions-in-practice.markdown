---
date: 2015-12-06 19:13:00
layout: single
classes: wide
title: Computation expressions and microphones
categories:
- programming
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

~~~ FSharp

      type SimplestBuilder () =
        member this.Bind(x,f) = f x          
        member this.Return(x) = x

~~~

  The `SimplestBuilder` type is a computation expression builder. "A builder is a record of operations that defines the semantics but also the syntax available in the block." [[Petricek, Syme (2014)](http://tomasp.net/academic/papers/computation-zoo/computation-zoo.pdf)]. In this case we are just saying that when `Bind` runs it will just call the function *f* with the parameter *x*. And when we call *Return* the function result will be the parameter passed into the function. The question here is how do they get called?, we answer this as follows:


  {% highlight FSharp  lineos %}

      let simple = new SimplestBuilder()

      let x =simple{
              let! one = "One"
              let! two = "Two"
              let! testing = one + two
              return testing}

  {% endhighlight %}

  When we see the definitions for `Bind` and `Return` those methods mandate how `let!` and `return` behave in the lines above (in this second code sample).
  We can say that the computation expression is everything after `let x =` declaration.

  The result of running the code sample is the following:

      >val x : string = "OneTwo"

  It might be worth remembering other computation expressions you might be already familiar with, such as.

#### Async workflows

  (workflow is a common alternative name for some computation expressions)

  {% highlight FSharp %}

      let extractLinks url =
          async {
              let webClient = new System.Net.WebClient()

              printfn "Downloading %s" url
              let html = webClient.DownloadString(url : string)
              printfn "Got %i bytes" html.Length

              let matches = System.Text.RegularExpressions.Regex.Matches(html, @"http://\S+")
              printfn "Got %i links" matches.Count

              return url, matches.Count
          };;

  {% endhighlight %}
  [[Example from wikibooks](https://en.wikibooks.org/wiki/F_Sharp_Programming/Async_Workflows)]

#### MBrace

{% highlight FSharp  lineos %}

    let remoteResult =
        cloud { printfn "hello, world" ; return Environment.MachineName }
        |> cluster.Run

{% endhighlight %}
[[Example from MBrace.io](https://github.com/mbraceproject/MBrace.StarterKit/blob/master/HandsOnTutorial/1-hello-world.fsx)]

In both examples the builder is defined elsewhere, and as consumers of the computation we have a set of things we can do. When we don't use the workflow with the expected syntax, (generally) the compiler will warn us with errors like:

> This control construct may only be used if the computation expression builder defines a 'ReturnFrom' method.

The builder works by using the compiler to convert the syntax into a block like this, for the SimplestBuilder we saw at the very start of this post:

{% highlight FSharp %}

    let y =
      simple.Bind("One", fun one ->
        simple.Bind("Two", fun two ->
          simple.Bind(one + two, fun testing ->
            simple.Return(testing))))

{% endhighlight %}

This de-sugared syntax (*syntax-max* if you will :) ) is harder to write and also harder to read.

![syntax-max]({{ site.images }}/syntax-max.jpg)

So this post tells us a little bit about what computation expressions are and how you can create very simple versions of them. In the [next post](http://www.roundcrisis.com/2015/12/06/more-computation-expressions/) we will see how to use them with a little more context.

Thanks for reading and happy holidays!!

![otter-xmas](https://s-media-cache-ak0.pinimg.com/236x/22/5d/fc/225dfc73941c511e67f628bf63bc6ac4.jpg)

  Yours Batmandrea
