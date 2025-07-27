---
date: 2025-04-20 00:13:00
layout: single
title: Testing a new modelling retro format - Gaps Growth Great Grind
categories:
- software-architecture
- retrospective
- systems
---

I've been running collaborative modelling sessions lately and noticed that some of the retrospective formats I tend to lean on don't work as well as it could, perhaps because they have other focus. I was thinking about how to better capture the type of thoughts that come up when you are working through a collaborative modelling session.

So, I be been trying a new format:

* 🕳️ Gaps: Is there anything not covered by this representation of the system that you think should be there , or it's not represented well. Example:  "We didn't model feature flags" "No idea what the department adjacent to us do with the data from our systems"
* 🌱 Growth: Are there some areas here that could give us an edge, alternatively some improvements. Example "Could System A and B send messages via Rabbit rather than have synchronous dependencies" 
* ✨ Great: Reasons you love this system representation or the system itself. Example: "It's great to see how our systems containers interact finally, I didn't have a full picture of this"
* 🚌 Grind:(as in daily grind). These are aspects that create unnecessary friction or complexity. For example are there  aspects of the system / this diagram that feel unnecessarily complicated or hard to use or understand.  Example: "This system always have items in the DLQ and it's never clear why... takes a long time to debug" or "The way we are diagramming this is not available to people in external departments"


The format seems to encourage more of the better types of feedback and discussions.