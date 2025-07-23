---
date: 2014-05-10 14:13:00
layout: post
title: Why F sharp and functional programming in general.
categories:
- programming 
- development
- f sharp
---

Why I have been learning F# (and functional programming in general) lately:

- It's functional first, so it encourages you to write pure functions and other cool stuff. 
- No more NullReferenceExceptions (wooohoo yeah! PARTY NOISES!!)
- Amazing type system. Think type inference on steroids and automatic generalization.
	* Tuples: it is great to be able to have multiple results for a function 
	* Discriminated Unions
	* Records
	* Moar. There are other f# Types
- Open source 
- Great community
- Great interop with C#
- Cross platform
- Type providers
- Forward pipe operator and the opposite
- It supports imperative and OO paradigms too
- F# interactive 


I though it would be good to expand on the points above

##Functional first

At some point during last year as I watched a talk by [Bodil Stokke][bodil], called [Programming, Only better][onlyBetter] (go watch all the videos of her talks, she is super smart you will learn a lot) in the talk she mentioned a paper called ["Out of the tar pit"][tar] both talk and paper made me think about the way I code. The end result of watching and reading was that I finally understood that side effect free code is better because it is simpler. We all know that writing simple code that does exactly what you imagine the code is doing is pretty damn hard, and functional programming can help making this a little simple. 
I feel that by trying to do a little synopsis of what the paper and Bodil said is doing a disservice to both, so go watch and read, beats whatever else you are doing :-D.  

This and going to [Code Mesh][codemesh] last year is what made me go from a person curious about functional programming, to "I have to learn and truly understand at least one functional programming right now!.

##No more NullReferenceException

The F# compiler will still have to deal with NullReferenceExceptions when dealing with .net types, however when dealing with Option type you can use pattern matching to match all the cases. 

{% highlight FSharp %}

let num = Some 1
let notnum = None

match num with 
| None -> printfn "num is None"
| Some x -> printfn "num is %i" x

{% endhighlight %}

There is an in-depth post about this [here][option].

## Amazing Type system

As a C# developer I always thought C#'s type system was pretty good, it did everything I expected, and rarely let me down. However, I am rather impressed by how much type inference and automatic generalization add to F#. Type inference allow the F# compiler figure out the types use and where, it does so in order top to bottom, left to right. I am thinking perhaps the only annoying side effect of this is that you have to set an order to  files in a project, something I find rather weird.
Anyway, when the compiler doesn't find what type to infer then (as far as I know)it makes the code general (imagine implementing that in C# :D) this happens because of automatic generalization (I have 90% confidence of this being correct)
I still don't know exactly how it all works but I am very happy with the results because I can try anything I want quickly. 
I guess F#'s type system was bound to be good, after all, static typing was first implemented in a functional programming language, . 

## Tuples

Tuples are one of the F# types, they represent a pair, triple or larger combination of types. This means you can finally do multiple return types :D

{% highlight FSharp %}

let personInfo =
    "Tayla", 45454545

let myFunction =
    let name, number = personInfo
    printfn "name is %s, number %i" name number
    printfn "Name is %s, number %i --" (fst personInfo) (snd personInfo)

{% endhighlight %}

	And this is what shows in f# interactive :

	name is Tayla, number 45454545
	Name is Tayla, number 45454545 --

	val personInfo : string * int = ("Tayla", 45454545)
	val myFunction : unit = ()

An advantage of using tuples is that when you are working with .net types that have out parameters, F# automatically turns that into tuples. Exmaple

{% highlight FSharp %}
open System.Collections.Concurrent

let convert =
    let collection = new BlockingCollection<int>() 
    collection.Add 4
    collection.TryTake()
{% endhighlight %}

	val convert : bool * int = (true, 4)

As you can see this returns convert : bool * int, when you see a * in the result section of f# interactive that means that the type is a tuple


## Records

Yet another F# type, I really like it because it makes classes definitions look like giganto-monsters. 
Also, tuples are great, but sometimes you want to name things so that ordering is not important.

{% highlight FSharp %}
type vector2Data = { x: float; y: float }

let equal = 
    let vect1 = {x = 1.0; y= 4.0}
    let vect2 = {y = 4.0; x= 1.0}
    vect1 = vect2

{% endhighlight %}


## Discriminated Unions

This is another f# type. I think an example will speak for itself.

{% highlight FSharp lineos %}

type Weapon = string
type Move = string
type Behaviour = string
type Character =
    | Player of Move * Weapon
    | NPC of Behaviour
    | Scenery

let jiro = Player("Throw", "Katana")
let tree = Scenery
let mempoWarrior = NPC("Chase")

{% endhighlight %}


The fsi console returns


	type Weapon = string
	type Move = string
	type Behaviour = string
	type Character =
	  | Player of Move * Weapon
	  | NPC of Behaviour
	  | Scenery
	val jiro : Character = Player ("Throw","Katana")
	val tree : Character = Scenery
	val mempoWarrior : Character = NPC "Chase"


As it's probably obvious this is a great way to work with finite set of choices, pattern matching can be used on discriminated unions.

## Open source

This is really what made me choose F# over other languages that I was considering learning. Since the language is open source and owned by the community, it is not tied to Microsoft and it's rather erratic decision making of the last few years. 
The C# interop just works.

## Great community

Many f# people in twitter and very vocal and welcoming. F# power tools is a must have add-on. But also: FAKE, FsCheck, Fuchu, many type providers.

## Supports imperative and OO paradigms

Being able to use pre-existing libraries and paradigms can be very useful.

## Great interop with C#. 

I'm sure there is a lot more to it, but the main thing for me is that it makes testing C# code shorter, and works both ways.  

## Cross platform. 

It runs on mono and there are people using F# with Xamarin tools for mobile. Also F# has an OCaml compatibility mode (that I haven't tested yet). The experience on non windows machines keeps improving. And in windows it is really nice once you get F# Power Tools. Before I installed that I found the significant whitespace a bit confusing, but now I literally can see what is the problem. 

## Type providers

This is a feature of F# 3.0, with them you get typed access to a wide variety of data sources, without requiring code generation. There are a few common type providers included . This means you can do a lot of data exploration with very little 

{% highlight FSharp %}
open FSharp.Data

type Languages = FSharp.Data.CsvProvider<"../languages_Ireland.csv">

let readLanguageData =     
    let path = "../languages_Ireland.csv"
    let data = Languages.Load(new FileStream(path, FileMode.Open))
    

{% endhighlight %}

That is pretty much all you need to start playing with the data of a csv file. And by playing I mean you have typed access to the fields in the csv.
This will print in the console the fist response (not a great use), but it show that it's typed, see the %s and that I can access fields by column name (it will use by default the first row for headers)

{% highlight FSharp %}
	let first = data.Rows |> Seq.head
    printfn "The first person production language %s" first.``What programming language(s) are you using in production?``

{% endhighlight %}

I don't know you, but I am totally blown away by this. There is also a graph tool that will help you plot data.

## Other people
Just for the craic (and to double check on my madness level) I asked on twitter what is people's preferred language feature and this is what I got:

<blockquote class="twitter-tweet" lang="en"><p><a href="https://twitter.com/silverSpoon">@silverSpoon</a> There are so many, pattern matching and active patterns are pretty awesome.</p>&mdash; Dave Thomas (@7sharp9) <a href="https://twitter.com/7sharp9/statuses/465168584382361600">May 10, 2014</a></blockquote>
<blockquote class="twitter-tweet" data-conversation="none" lang="en"><p><a href="https://twitter.com/silverSpoon">@silverSpoon</a> Because they dramatically simplify logic processing and collapse a lot of boilerplate.</p>&mdash; Dave Thomas (@7sharp9) <a href="https://twitter.com/7sharp9/statuses/465168797411069952">May 10, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
<blockquote class="twitter-tweet" data-conversation="none" lang="en"><p><a href="https://twitter.com/silverSpoon">@silverSpoon</a> I just love pipe forward and pipelines of functions. Simple, and makes workflows / data transforms super clear.</p>&mdash; Mathias Brandewinder (@brandewinder) <a href="https://twitter.com/brandewinder/statuses/465200532231958528">May 10, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
<blockquote class="twitter-tweet" lang="en"><p><a href="https://twitter.com/silverSpoon">@silverSpoon</a> quotations are very cool</p>&mdash; gregyoung (@gregyoung) <a href="https://twitter.com/gregyoung/statuses/465043534161379328">May 10, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
<blockquote class="twitter-tweet" data-conversation="none" lang="en"><p><a href="https://twitter.com/silverSpoon">@silverSpoon</a> What I miss the most in C# is DUs. To make them usable you need pattern matching.</p>&mdash; Robert Jeppesen (@rojepp) <a href="https://twitter.com/rojepp/statuses/465170677834997760">May 10, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
<blockquote class="twitter-tweet" data-conversation="none" lang="en"><p>.<a href="https://twitter.com/silverSpoon">@silverSpoon</a> Function currying because, like curry, once you start using it you can&#39;t stop</p>&mdash; Patrick McDonald (@PaddyMcDonald) <a href="https://twitter.com/PaddyMcDonald/statuses/465181555074531329">May 10, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
<blockquote class="twitter-tweet" data-conversation="none" lang="en"><p><a href="https://twitter.com/silverSpoon">@silverSpoon</a> <a href="https://twitter.com/nikhilsingh">@nikhilsingh</a> favorite feature <a href="https://twitter.com/search?q=%23fsharp&amp;src=hash">#fsharp</a> Data.SqlClient, I use every day, it works, authors very responsiv&#10;<a href="https://t.co/9y3H8LzOF4">https://t.co/9y3H8LzOF4</a></p>&mdash; Jack Fox (@foxyjackfox) <a href="https://twitter.com/foxyjackfox/statuses/465242438970265600">May 10, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
<blockquote class="twitter-tweet" data-conversation="none" lang="en"><p><a href="https://twitter.com/silverSpoon">@silverSpoon</a> <a href="https://twitter.com/c4fsharp">@c4fsharp</a> piping stuff because you it gives an exellent flow to things</p>&mdash; Erlend Wiig (@ErlendW) <a href="https://twitter.com/ErlendW/statuses/465256913878663169">May 10, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>



## Summary

It might seem like there is a lot to know to just even get started, but I think if you just jump right in, you have a lot to win. Most of the names of the features come from a maths background, it can feel a bit of putting, but it's really not that bad.
Maybe it's because diving into a new language is just new and exciting, but it's been a while since my brain reacts so positively to learning something new. Sometimes I get stuck but then that's when the community aspect really kicks in.

## Resources

- Books:
	* [Expert F# 3.0 by Don Syme, Adam Granicz, Antonio Cisternino](http://www.apress.com/9781430246503)
	* [Real world functional programming by Tomas Petricek with Jon Skeet](http://www.manning.com/petricek/)

- [F# for fun and profit](http://fsharpforfunandprofit.com/)
- [Phil Trelford blog](http://trelford.com/blog/)
- [Thomas Petricek blog](http://tomasp.net/blog/)
- [Community for F#](http://c4fsharp.net/)
- [F# foundation](http://fsharp.org/)



Another good talk about functional programming for the OO developer [from Jessica Kerr](https://vimeo.com/78909069) 

### Any questions, comments and corrections very welcome as always


[tar]:http://shaffner.us/cs/papers/tarpit.pdf
[bodil]:https://twitter.com/bodil
[onlyBetter]:https://vimeo.com/74452549
[option]:http://fsharpforfunandprofit.com/posts/the-option-type/
[codemesh]:http://codemesh.io