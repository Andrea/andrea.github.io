---
date: 2014-02-11 12:13:00
layout: post
title: Replay systems notes 1
categories:
- replay-systems
- c#
---

* Apparently two alternatives: save input or save scene data 
* Input based seem to require a deterministic game engine, what is the cost of making our engine deterministic?
* Since we need this for debugging purposes, it is useful to have as much debug data as possible then saving scene data seems like a better approach, how to get the non serialized data? is that a requirement?

Spiking a replay system
*  Added status and thinking I might need time deltas to be saved so that when we replay we replay the scenes in the same time deltas, it seems like too much data but it might make a difference 

### Research links

- [Rewindable replay by Mark Wesley][mw1]
- [In depth Unity replayed][gs]


[mw1]:http://gdcvault.com/play/1018138/Implementing-a-Rewindable-Instant-Replay
[gs]:http://www.gamasutra.com/view/news/174342/Indepth_Unity_replayed.php