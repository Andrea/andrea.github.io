---
date: 2014-12-12 11:44:00
layout: post
title: FSharp and games in celebration times
categories:
- programming 
- development
- Fsharp
---

The title of this post was a bit obscure as I didn't really know what I was going to do for this entry on the [#FsAdvent calendar](https://sergeytihon.wordpress.com/2014/11/24/f-advent-calendar-in-english-2014/)
Make sure you check out the previous entries in the series.

For today, I thought we would celebrate with sound, in the Key of F# :D

To that effect we can use OpenAl. To be honest this was a little be more difficult to do that it needed to be, mostly because there was plenty of playing around with values to make sure stuff worked and sounded somewhat ok.

The good thing about this is that you can run the sample off in F# interactive (make sure you change the path to your location of OpenAl, you should get the NuGet package called OpenTKWithOpenAL)
To start off you need a context, a buffer and a source

{% highlight FSharp %}

        use audioContext = new AudioContext()
        let buffer = AL.GenBuffer()
        let audioSourceIndex = AL.GenSource()

{% endhighlight %}

Then we need to get something to play, if our input is a string with the whole song then we can do something like this:

{% highlight FSharp %}

    let toFrequency note =
        match note with
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

The frequencies can be found [here](http://liutaiomottola.com/formulae/freqtab.htm)

Then, with some research into the OpenAl docs this is how we can convert those frequencies into data that can be played.

{% highlight FSharp %}

    let samplingFrequency = 44100
    let samplingFrequency' = float samplingFrequency
    
    let generateNote (freq:float32) =
        let noteLength = 0.5
        let seqLength = int  (samplingFrequency' * noteLength)
        Seq.init seqLength (fun i -> 
                    (2.0 * Math.PI * float freq) / samplingFrequency' * float i
                        |> Math.Sin                        
                        |> ( * )  (float Int16.MaxValue)
                        |> int16
                        )

{% endhighlight %}

the idea here is that you do magic xMas stuff that means you make a wave with the following shape. We are limiting all sounds to be of the same length, however it seems like it would be fun to also change the length of each tone.

![waves](images/waves.png)

After that you need to combine this to return the complete sequence, here 'Seq.collect' really shines

{% highlight FSharp %}
        let freqToWaves = toFrequency >>  generateNote
        let data = notes                        
                        |> Seq.collect freqToWaves                        
                        |> Array.ofSeq
{% endhighlight %}

Finally we use OpenAl to actually play the data

{% highlight FSharp %}

        AL.BufferData (buffer, ALFormat.Mono16, data, data.Length * 2, samplingFrequency)
        AL.Source(audioSourceIndex, ALSourcei.Buffer, buffer)
        AL.SourcePlay(audioSourceIndex)

{% endhighlight %}

There is a mystery song you can play (in the key of F#).

You can find the complete sample [here](https://gist.github.com/Andrea/9212fa6249545d3987a9)


### Summary

Try it, you will probably love it. Another little toy to play with during the jolly season.