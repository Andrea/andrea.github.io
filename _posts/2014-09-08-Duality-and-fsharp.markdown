---
date: 2014-09-08 11:44:00
layout: single
classes: wide
title: Writing Duality Components in FSharp
categories:
- programming 
- development
- Duality
---


Duality is a 2D game engine with an extensible editor (If you follow my blog you'll see it mention it a few times), I added F# Scripting support a good while ago but I haven't been posting too much about it, I probably should change that. 

Scripting is not the only way to use F# on this engine, you can also create components with F# and it's pretty simple.

When you run Duality on a folder that has no Data, it creates a solution for plugins by default in Source/Code with two projects: CorePlugin and EditorPlugin. Open the solution and add a F# project. Once it's created open the project properties and change the assembly name so that it ends with "core"

![EndInCore](http://i.imgur.com/ygczgM7.png)

* Add a reference to Duality.dll and OpenTk.dll (you will find this on the game folder, alternatively have nuget packages too in [MyGet](https://www.myget.org/F/6416d9912a7c4d46bc983870fb440d25/) )
* Add a new file to the project, it must inherit from Core and read like this 

{% highlight FSharp%}
open Duality

type BreakoutFSharpCorePlugin() = 
    inherit CorePlugin()
{% endhighlight %}

Lastly if you want to F5 to launch the editor you can add the following to the end of Editor.csproj.user file (replace DualityEditor.exe locations )

{% highlight xml %}
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)' == 'Debug|AnyCPU'">
    <StartAction>Program</StartAction>
    <StartProgram>Pathto\where\editor\is\DualityEditor.exe</StartProgram>
    <StartWorkingDirectory>Pathto\where\editor\is</StartWorkingDirectory>
  </PropertyGroup>
<PropertyGroup Condition="'$(Configuration)|$(Platform)' == 'Release|AnyCPU'">
    <StartAction>Program</StartAction>
    <StartProgram>Path\to\DualityEditor.exe</StartProgram>
    <StartWorkingDirectory>Path\to\where\the\game\is</StartWorkingDirectory>
  </PropertyGroup>

{% endhighlight %}

####Example
This is an example of a component

{% highlight FSharp%}

open Duality
open System

[<Serializable>]
type ScoreComponentF() = 
    inherit Component()
    let mutable score =0

    member this.Score = score
    
    member this.IncreaseScore amount =
        score <- score + amount  


{% endhighlight %}
