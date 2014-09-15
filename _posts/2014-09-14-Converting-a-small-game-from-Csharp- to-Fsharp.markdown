---
date: 2014-09-15 11:44:00
layout: post
title: Converting a small game from C# to F# part 1
categories:
- programming 
- development
- Duality
- Fsharp
- Csharp
---

As part of the workshop I am preparing to run on a bunch of places in North America, I created a small clone of Breakout and just ported it to F#. I am going to be explaining a little about how the engine works and that will be intertwined with an (hopefully) fun intro to F#.

Duality is 

* A 2D game engine that comes with an extensible visual editor.
* OSS (MIT license).
* Written on C# and OpenTK.
* the architecture is built around a plugin system.

Follow the link for Adam's [getting started](https://github.com/AdamsLair/duality/wiki/Getting-Started).

In the [previous post](http://www.roundcrisis.com/2014/09/08/Duality-and-fsharp/) I showed how to create components in Duality, so I started of with one the simplest component, ScoreComponent, that component looked like this

{% highlight c# %}

    [Serializable]
    public class ScoreComponent : Component, ICmpUpdatable
    {
        private int _score;

        public int Score { get { return _score; } }

        public void IncreaseScore(int amount)
        {
            Score += amount;
        }

        public void OnUpdate()
        {
            var textRenderer = GameObj.GetComponent<TextRenderer>();
            if (textRenderer != null) 
                textRenderer.Text.SourceText = "Score: "+ Score;
        }

    }

{% endhighlight %}

When converting to F# it looks pretty similar, at least initially

{% highlight FSharp%}
[<Serializable>]
type ScoreComponentF() = 
    inherit Component()

    let mutable score =0

    member this.Score = score
    
    member this.IncreaseScore amount =
        score <- score + amount        
    
    interface ICmpUpdatable with 
        member this.OnUpdate() =
            let textRenderer = this.GameObj.GetComponent<TextRenderer>()
            if (textRenderer <> null) then
                textRenderer.Text.SourceText <- sprintf "Score: %i"  this.Score
{% endhighlight %}


The method **OnUpdate** could be improved. A first iteration would look like:

{% highlight FSharp%}

    interface ICmpUpdatable with 
        member this.OnUpdate() =
            match this.GameObj.GetComponent<TextRenderer>() with
            | null -> ()
            | textRenderer -> textRenderer.Text.SourceText <- sprintf "Score: %i"  this.Score

{% endhighlight %}

This is nice but this pattern(?), do something if the component exist, is rather common and it would be nice to turn this into an option type.


We will continue in the next post :D

Fun and games FTW!! 

OT: Best of luck to all the people involved in Minecraft and this transition to Microsoft. I can emphatize with where [@notch](http://twitter.com/notch) is coming from.