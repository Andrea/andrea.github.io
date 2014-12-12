---
date: 2014-12-12 11:44:00
layout: post
title: FSharp and games in celebration times
categories:
- programming 
- development
- Fsharp
---

The title of this post was a bit obscure as I didn't really know what I was going to do for this entry on the [#FsAdvent Calendar](https://sergeytihon.wordpress.com/2014/11/24/f-advent-calendar-in-english-2014/)
Make sure you check out the previous and future entries in the series.

For today, I thought we would celebrate with sound, in the Key of F# :D

![meowmoew](http://i.imgur.com/3rYHhEu.jpg) src [reddit](http://www.reddit.com/r/aww/comments/2p2r01/our_indoor_cat_moved_from_a_gray_apartment_block/)

To that effect we can use OpenAl. To be honest this was a little more difficult to do that it needed to be, mostly because there was plenty of playing around with values to make sure stuff worked and sounded somewhat ok. 

The good thing about this sample is that you can run the sample either via a console app or in F# interactive (make sure you change the path to your location of OpenAl, you should get the NuGet package called OpenTKWithOpenAL) Disclaimer this is the first time I play with vanilla OpenAl (it will probably show).

#### Bird's eye

The end goal is to transform something like this ``"F# F# G# F# F# D# D# D# F# F# G# F# F# D# D# D#" `` into a collection of numbers that represent a wave, then we can feed that into OpenAl for it to play. 
The graph below represent one note (generated with [F# Charting](http://fsharp.github.io/FSharp.Charting/)) 

![waves](http://www.roundcrisis.com/images/waves.png)

#### Step by Step

To start off you need a context, a buffer and a source, these are OpenAl requirements.

{% highlight FSharp %}

use audioContext = new AudioContext()
let buffer = AL.GenBuffer()
let audioSourceIndex = AL.GenSource()

{% endhighlight %}


Then we need to get something to play, if our input is a string with the whole song then we can do something like this to get the frequencies calculated for each note

{% highlight FSharp %}

    let toFrequency (note:string) =
        match note.ToUpper() with
        | "C" ->  261.626f
        | "C#" -> 277.183f
        | "D"-> 293.665f
        |"D#"-> 311.127f
        |"E"-> 329.628f
        |"F"-> 349.228f
        |"F#"-> 369.994f
        |"G"-> 391.995f
        |"G#"-> 415.305f
        |"A"-> 440.0f
        |"A#"-> 466.164f
        |"B"-> 493.883f
        |_ ->  369.994f (*Defaults to F# because xMas ;) *)

{% endhighlight %}

I was thinking we could have a discriminated union here, however this seemed to serve the purpose of this example in a simple and concise way. 

You might be wondering how I came to those numbers, well turns up the internet is great for this sort of thing, they can be found [here](http://liutaiomottola.com/formulae/freqtab.htm). Tried a few octaves and these were the ones I preferred.

Then, with some research into the [OpenAl docs](http://www.opentk.com/node/209) and a bit of reading into [Duality's source code](https://github.com/AdamsLair/duality) this is how we can convert those frequencies into data that can be played.

{% highlight FSharp lineos %}

    let samplingFrequency = 44100.0    
    
    let generateNote (freq:float32) =
        let noteLength = 0.5
        let seqLength = int  (samplingFrequency * noteLength)
        Seq.init seqLength (fun i -> 
                    (2.0 * Math.PI * float freq) / samplingFrequency * float i
                        |> Math.Sin                        
                        |> ( * )  (float Int16.MaxValue)
                        |> int16
                        )

{% endhighlight %}

As mentioned in the first section, we are using 44100 as the base frequency, to simplify things the note length is set to half a second, however this is something that could be easily changed to support different lengths.
Then we are creating a **sequence** that is half the frequency, and the reason for that is this is the number of samples required. Each item in that sequence is part of a curve that represents the sound for that given note (the freq parameter). 

With those two key functions you can create the complete collection. In this case Seq.collect really shines, it is perfectly suited to what we need to do:

> Combines the given enumeration-of-enumerations as a single concatenated enumeration.


{% highlight FSharp %}

        let freqToWaves = toFrequency >>  generateNote
        let data = notes                        
                        |> Seq.collect freqToWaves                        
                        |> Array.ofSeq
{% endhighlight %}

Finally we use OpenAl to actually play the wave:

{% highlight FSharp lineos %}

	AL.BufferData (buffer, ALFormat.Mono16, data, data.Length * 2, samplingFrequency)
	AL.Source(audioSourceIndex, ALSourcei.Buffer, buffer)
	AL.SourcePlay(audioSourceIndex)

{% endhighlight %}



<small>There is a mystery song you can play (in the key of F#)</small>

You can see it all together in this sample [here](https://gist.github.com/Andrea/9212fa6249545d3987a9)


### Summary

Try it, you will probably love it. Another little toy to play with during the jolly season.


Thanks to Sergey and the F# community for this cool [FsAdvent](https://sergeytihon.wordpress.com/2014/11/24/f-advent-calendar-in-english-2014/).

Also thanks to everyone (yes you, you rock!) for a truly amazing year. 

The gif below seems completely unsuitable but you are here already :) 

<img src="http://www.gifbin.com/bin/052011/1305562847_skiing-ostrich.gif">