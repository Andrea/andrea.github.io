---
layout: post
title:  "Multithreaded game engine -Using Concurrent collections instead"
date:   2013-06-22 21:40:10
categories: ""
---

So, while I was trying to implement the double buffer (previous post available [here][1]) I started thinking about perhaps a simpler implementation with one of the concurrent collections, so I tried with a [ConcurrentQueue&lt;T>][2].

The idea behind it is pretty simple. Instead of having the two collections of RenderCommand we have a ConcurrentQueue&lt;RenderCommand[]> so we think of each of the elements of the queue as a frame, ready to be rendered.

As before, we are starting off with the primitives3DWindows sample. A bit obvious, but, we’ll need to initialize the queue on the constructor of the Renderer class(I just thought I’d mention that).

From the world We’ll add all necessary cubes to a renderCommand, using the AddCube() method. At the end, we’ll need to add that collection to the queue by calling EndFrame(). Like this

{% gist 8195397 %}

These methods are public because they are called from World, however, as you can see from the sequence diagram below we check if the renderer CanAcceptCommands(), the reason for this is that we don’t regulate how often we run world.Update() and in reality we only want to have one frame (or RenderCommand collection ready to render) when we call Draw so that there is no latency.

![alt text](http://roundcrisis.files.wordpress.com/2013/06/capture.png "Update Loop")

With the update done, we now need to render. At this point this is pretty trivial. Code below

{% gist 8195523 %}

I think what is happening here is pretty self explanatory, but I will do it anyway.  If we call Draw() and we TryDequeue and we can’t we call return, there is no point in trying to Draw and empty array of RenderCommands (I believe that would be the result). Alternatively if we successfully dequeue, we will let the CubePrimitive draw each of the commands.

### Analysis

It seems to me that this implementation is easier to follow and implement that the previous one, however I took some performance data and this is the result:

Double Buffer
![alt text](http://roundcrisis.files.wordpress.com/2013/06/image.png "Update Loop")

Concurrent Queue
![alt text](http://roundcrisis.files.wordpress.com/2013/06/image1.png "Update Loop")

Green means execution time, and red means synchronization time.

I think what these graphs tell is that double buffer is more efficient because concurrentqueue uses spin waits to synchronize, so it shows up in the thread analysis as execution time, where the previous double buffer implementation shows up as synchronization time, meaning the threads are just asleep.

Next I’m going to try with a concurrent collection that doesn’t use spin wait: BlockingCollection&lt;T&gt;.


[1]:[http://roundcrisis.com/2013/05/24/multithreading-rendering-in-a-game-engine-with-cdouble-buffer-implementation/] 
[2]:[http://msdn.microsoft.com/en-us/library/dd267265.aspx] 
[6]:[http://msdn.microsoft.com/en-us/library/dd267312.aspx]