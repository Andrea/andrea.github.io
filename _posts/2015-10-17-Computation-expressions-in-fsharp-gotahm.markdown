---
date: 2015-10-18 19:13:00
layout: post
title: FSharp Gotham - Experience report
categories:
- programming
- development
---

![F# Gotham](https://d4cdtj2t27jdu.cloudfront.net/conference_logos/cropped_b7df0c8238.jpg)

[F# Gotham](http://www.fsharpgotham.com/) stared on the morning of the 16th of October at [Jet's]() Offices (lovely views of the city)

![view](http://www.roundcrisis.com/images/jet-view.jpg)


I saw the very start of [Riccardo Terrel's](https://twitter.com/TRikace) tutorial on Reactive and Concurrent F#. He was covering  the practical aspects of writing safe concurrent programs, and how to do that with functional programming languages, in particular F# . Sadly I was rehearsing my talk. From the distance it looked fun.


Then it was my turn, I talked about Computation Expressions, the idea of this talk is to introduce them, trying to demistify them a little bit with the help of awesome pictures of otters :D
We covered some well known CEs such as async, error handling monads as well as mbrace.

There is an extensive list of resources at the end of the
[slides for my Computation Expressions in Context ](http://www.roundcrisis.com/presentations/2015-fsharp-gotham-computation-expressions/index.html#/).

Then it was time for two people from Microsoft to answer some questions. David Stevens, the new Programme Manager for F#, started this talk with a brief history of the language and some features of the language he particularly liked, and some extra information trying to give people some context of where he was coming from. Great presentation.
This was followed by some questions from the audience, Jay Schmelzer, one of the directors from DevDiv, joined David. The questions varied from feature parity to marketing support, azure, the collaboration with the F# Software Foundation and more.
I think we got some very honest as well as some promising answers. I am looking  forward to see how it all goes and the near and distant future. I believe all  sessions have been recorded and will link it here as soon as they becomes available.

Next it was lunch time and time to mingle. Great food. Kudos to the organisation team and the sponsors, for putting on a great event.
[Update 21-10-2015] There is an article on [InfoQ](http://www.infoq.com/news/2015/10/fsharp-gotham) with more details about this talk.

![Charles and Riccardo]({{ site.images }}/fs-gotham/c_a_r.jpg)

Then it was time to listen to [Charles Petzold](https://en.wikipedia.org/wiki/Charles_Petzold) talk about Using F# for Xamarin forms. He started off talking about his early career as a Programmer using Fortran and APL amongst other languages.
Then he built a series of samples targeting multiple devices using Xamarin Forms with F#.
He showed:

* How to setup the solution so you can use F# (it might be a  idea to create a template for this type of solution)
* Deployment to many devices.
* A Sieve of Eratosthenes in 3 or 4 lines of code (yay!)
* Converting the code to work asynchronously

and more. Nicely presented.
I wish I could find a way to contact him to let him know about [Paket](https://fsprojects.github.io/Paket/), I think he might appreciate it.

![xam]({{ site.images }}/fs-gotham/t2.jpg)

Then it was time for the optimization panel with Jon Harrop, Jack Pappas, and Lev Gorodinski. MCed by Paulmichael Blasucci. This was a highly interactive session  where we heard about collections and data structures (how they always turn up on these type of conversations.... :D) common things to avoid and some very funny war stories.
One of the questions was about a particular [post](http://flyingfrogblog.blogspot.com) Jon Harrop had posted a few years ago doing a language comparision, and how that evolved and how it compared to now. There was also some discussion on tooling  where the usual ones turned up VS interated one , Concurrency visualization, roll your own, and also one I heard of but never used, [Perf View](http://www.microsoft.com/en-ie/download/details.aspx?id=28567). I was kind of suprised no one mentioned dotTrace and dotMemory.


Finally Phil Trelford closed the conference with a talk that I am lucky to have seen multiple times, his "Write your own compiler in 24 hour" talk. It is funny how you always pick up new things when you watch something a couple of times. This time I was looking at how focused on the process of writing the compiler, starting with the parser and testing out his design before moving off to implementing the AST.
This made me think about something else we were discussing on a "hallway session" about how do we make decisions when you have limited knowledge, my take on it is you choose a path and try to do a very small implementation trying to fail fast, as fast as possible, focusing on how is it failing , iterating and then implementing a solution you know does what it should do.

![phil]({{ site.images }}/fs-gotham/t3.jpg)


Another thing that was really cool about this conference was the one track and highly relaxed feeling around it (lots of space, comfortable sitting).

Since I was wearing a cape that was given to all of us as swag, someone called me BatmAndrea, I think I'll keep this :)

Yours BatmAndrea
![view]({{ site.images }}/fs-gotham/view2.jpg)
