---
date: 2014-12-12 11:44:00
layout: post
title: FSharp and games in celebration times
categories:
- programming 
- development
- Fsharp
- AI
- Conferences
---

The title of this post was a bit obscure as I didn't really know what I was going to do for this entry on the [#FsAdvent calendar](https://sergeytihon.wordpress.com/2014/11/24/f-advent-calendar-in-english-2014/)
Make sure you check out the previous entries in the series.

For today, I thought we would celebrate with sound, in the Key of F# :D

To that effect we can use OpenAl. To be honest this was a little be more difficult to do that it needed to be, mostly because there was plenty of playing around with values to make sure stuff worked and sounded somewhat ok.

The good thing about this is that you can run the sample off in F# interctive (make sure you change the path to your location of OpenAl, you should get the Nuget package called OpenTKWithOpenAL)
To start off you need a context, a buffer and a source

{% highlight FSharp %}

        use audioContext = new AudioContext()
        let buffer = AL.GenBuffer()
        let audioSourceIndex = AL.GenSource()

{% endhighlight %}

Then we need to get something to play, if our input is a string with the whole song then we can do something like this:
