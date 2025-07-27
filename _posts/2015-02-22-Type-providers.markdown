---
date: 2015-02-22 19:44:00
layout: single
classes: wide
title: Type providers
categories:
- type providers
- fsharp
- squirrels

---

The awesome [Rachel](http://rachelree.se/) and myself were on [Mostly Erlang podcast](http://mostlyerlang.com/) the other day (it's not live yet), check it out they have some very cool episodes.

Anyway I was there and we were talking about Type providers and I said something around the lines of "type providers generate erased types..." blah. This is not correct so this post is an attempt to cure that mistake. (I could tell you how I woke up at 5am the next morning and realised I said something wrong and someone was there to record it but, don't worry I won't).

#### Anyway, what is a type provider?

I was at a talk somewhere a year+ ago. All I remember is that 3 lines of code gave me access to typed info from a source (in that case a csv) without any further setup, I though **Wow**, all that wasted time!, No more!! I was thinking of all the mapping I had done with ORMs or using something like FileHelpers + setup (that would need to be changed if the data changed even a little bit). 

so like 5 seconds later we were all thinking ... how does it work?

According to [msdn](https://msdn.microsoft.com/en-us/library/hh156509.aspx): "A type provider is a component that provides types, properties and methods" thanks Sherlock :D I hope it got better but I got bored ... so I moved on to other sources.

Like this paper: [Strongly-Typed Language Support for InternetScale Information Sources](http://research.microsoft.com/pubs/173076/information-rich-themes-v4.pdf), and that has better info, 

  "A type provider is a compile-time component that [...] provides two things to the host compiler/tooling:

  1. A provided component signature,... that is computed **on-demand** as needed by the compiler 
  2. A provided component implementation of the component signature.  This is given by either an actual .NET assembly that implements the component signature (the generative model for the provided types), or, a pair of erasure  functions giving  representation  types  and  representation expressions for the provided types and provided methods respectively (the erasure model for the provided types).

  [...]Essentially, a type provider is an adapter component that reads schematized data and services and transforms them into types in the target programming language. [...]

  A type provider does not necessarily contain any types itself; rather, it is a component for generating descriptions of types, methods and their implementations. A type provider is thus a form of compile-time meta-programming, a compiler plugin with access to the external world that augments the set of types that are known to the type-checker and compiler."

I found this significantly more informative. I hope you too :)
One thing to note here (I made it bold and all) is the "on demand" meaning that (steals again from the paper) "the provided type space can be very large or even infinite."

The other thing I found interesting is that you can implement a component by generation or erasure. The erasure bit , as far as I understand, is that the type looks like a normal type at compile time, but during runtime it's erased to a common type.  So there is less overhead. 


I am sure you have seen examples of usage of type providers, I particularly like the csv one 

{% highlight FSharp %}

  [<Literal>]
  let path = "..\IrelandProgrammingLanguages.csv"  
  type Languages = CsvProvider<path>
  let data = Languages.Load(new FileStream(path, FileMode.Open))
  let languageCount = Seq.toList data.Rows
                        |> List.map ( fun r -> splitAndCount r.``What programming language(s) are you using in production?``)     


{% endhighlight %}

The first line is just a path, in the second line we create a type using the CsvType provider passing the path as a parameter. To load the data from the csv we call Load. Finally the last line is actually using the data provided, where one of the column names on the csv file is ``What programming language(s) are you using in production?`` .


![squirrel](http://i.vimeocdn.com/portrait/1954123_300x300.jpg)


If you are into type providers, you need to know [Ross McSquirrel](http://www.pinksquirrellabs.com/)(I might have made up a better last name for him), check out his talk [about Ridiculous type providers ](https://skillsmatter.com/skillscasts/6126-where-no-type-has-gone-before)(again I might have given the talk a new and hopefully better name :D).


I was going to write about creating type providers, but [this 2 part post](http://blog.mavnn.co.uk/type-providers-from-the-ground-up/) by [Michael Newton](https://twitter.com/mavnn) beat me to it (by about a year) :D and it's worth checking it out to understand how this cool language feature works.
