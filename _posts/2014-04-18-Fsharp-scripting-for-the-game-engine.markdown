---
date: 2014-04-21 14:13:00
layout: post
title: F# scripting for a component based game engine
categories:
- programming 
- development
- f sharp
---


Recently [Andrew][bsa] added C# scripting capabilities to [Duality][dua], the engine we are using to build [Honourbound][hon]. Once we had something working, we started thinking about the fact that it might be pretty simple to add support for [F#][fsh], so we did. 

A few weekends ago I twitted this:

![tweet]({{ site.images }}/2014-04-20-fhscripting-tweet.JPG)

We had a spike working within a few hours with an old version of F# codedom. I spent some time the last few days making it more usable within the editor.

## How to use

If you are like me, you'll want to try this out as soon as possible, instructions :D 

Steps to move a gameObject with an F# script if you never used Duality

- Download duality with the plugins in place from this [link][dualityWithPlugins].
- Open DualityEditor a scene will be created by default but not saved, save it. 
- Drop a duality logo from the default folder in Project View into the main area. This will create a GameObject with a 
- In the game object in the object inspector (if you don't see it, menu->View-> Object Inspector), right click and add a script component.
- In the scene editor, create a folder, call it scripts, right click and go to Scripting -> F sharp script
- Double clicking on the newly created resource will open the F# file with your default editor for files ending with .fs.
- You will have access to the GameObject and other engine related properties the same way you do in Duality (or Unity if you are familiar with it) 

{% highlight FSharp %}

module Dualityscript

open ScriptingPlugin
open Duality
open Duality.Components
open Duality.Helpers
open OpenTK

type FSharpScript() =
    inherit DualityScript()

    override this.Update()=        
        this.GameObj.Transform.Pos <- this.GameObj.Transform.Pos + new Vector3(1.0f,0.0f,0.0f)

{% endhighlight %}

If you want to build all yourself :

- Build from [source from our fork][dualityFork]. We are using our fork of Duality instead of Adams, because of some dependencies we have on our own fork, we will see how to make this a better experience, so far I wanted to get something usable out.
- Build [this][dscr] get the ScriptingPlugin.core.dll and ScriptingPlugin.editor.dll and copy them into the plugins folder inside the aforementioned Game folder.
- from the packages folder copy FSharp.Compiler.Services.dll
- from the packages folder copy Mono.cecil.dll and Mono.cecil.pdb.dll

A video showing this [here][video].

## Why


Game programming in a middle to big sized project falls into three logical categories. Those categories are associated with their level of use: i.e: how often you run this code, and the rate of change i.e. how many times this file has changed in the last month. 

**Engine**: Core game engine, doesn't change too often, ideally it has lots of test coverage.

**Game Systems**: These are game specific systems that are core to the game, the change more often than the engine. This code has a high re usability level so should be tested. 

**Gameplay**: The code here changes all the time, the general pattern is a lot of initial churn and then some tweaks. We agreed not to test this code, tho there are some exceptions. 

I think using F# with a functional approach in our GamePlay code will make us more efficient because of the frequency of change this type of code requires. It might help reduce the number of NullReferenceException type of errors too.

## Thanks

 [dualityWithPlugins]:https://www.dropbox.com/s/i9stp1z0avihzvq/DualityWithPlugins.zip
 [bsa]:http://github.com/bravesirandrew
 [dua]:http://github.com/adamslair/duality
 [dualityFork]:http://github.com/bravesirandrew/duality
 [hon]:http://digitalfurnacegames.com
 [djf]:http://fsharp.org/
 [dualityBuild]:https://www.dropbox.com/s/2tjbdnp6h8foju2/Duality.zip
 [dscr]:https://github.com/BraveSirAndrew/DualityScripting
 [video]:http://youtu.be/HcnNGIeOnPc