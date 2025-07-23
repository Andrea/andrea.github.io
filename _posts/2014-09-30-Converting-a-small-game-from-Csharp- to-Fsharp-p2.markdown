---
date: 2014-09-30 11:44:00
layout: post
title: Converting a small game from C# to F# part 2
categories:
- programming 
- development
- Duality
- Fsharp
- Csharp
---

This post could also be called:One step forward, two steps backwards.

I thought I should rewind a little bit, and have an overview of the game before we continue.

The C# version of the game has 9 files and each, each has a class where (generally a component is defined), I decided to change this for the F# version of the game, tho I am not sure type per file is an idiom of F# or not. (Comments on this, really welcome)

The idea of doing this port is to show the progression of the code from C# to F# to (hopefully) better F# so if you have some comments on how to improve, they are super welcome, particularly commenting with code samples (or PRs). The whole game (in C# and F# and the editor ) is all available from [this github repo](https://github.com/Andrea/FSharpAndGamesBreakout).

### About Duality

The engine, Duality, is a C# engine that follows some of the C# idioms. It is not in our immediate plans to make a wrapper to make the engine more f# friendly, I find don't find it too hard to work with the two languages, however it might be because I am familiar with it enough to not feel much of the pain.

These are bits of code we will se over and over

#### Is it a bit humid here?

Declaring a component. Needs to be serializable, and inherit from component

{% highlight fSharp %}

[<Serializable>]
type LifeMeter() = 
    inherit Component()  

{% endhighlight %} 


Most of these components will need to implement ```ICmpUpdatable``` or ```ICmpInitializable```

{% highlight fSharp %}

    interface ICmpUpdatable with 
        member this.OnUpdate() =
            //Do some componenty stuff here

{% endhighlight %} 

Some components need to be able to detect collisions, on those situations you need to implement ```ICmpCollisionListener```
{% highlight fSharp %}

    interface ICmpCollisionListener with 
        member this.OnCollisionBegin (_, args)=
			// Do collision stuff here (or somewhere else)           
        member this.OnCollisionEnd(_,_)=  
            ()
        member this.OnCollisionSolve(_,_)=  
            ()

{% endhighlight %} 

I don't think I mind the interface implementations.

Then there is the find the (not null) component. In the example below we are looking for a ```TextRenderer``` within the object. In the None matching, it is more likely you want to log and editor warning, rather than do nothing

{% highlight fSharp %}

            let tr = OptionComponent<TextRenderer> this.GameObj
            match tr with
            | None -> ()
            | Some tr ->tr.Text.SourceText <- sprintf "Score: %i"  score

{% endhighlight %} 



What does all of this mean? well I though it might be useful to summarize what I have seen so far.  I'll update this post with more if I think of any other repeating pattern.

Until the next time :D
