---
author: roundcrisis
comments: true
date: 2018-04-26 10:48:00+00:00
layout: single
classes: wide
title: TIL in Purescript
categories:
- Purescript
---

I am learning a little bit of [Purescript] and today I learned:

Custom infix operators (unsuprisingly) don't work on Psci (the Purescript REPL)

Function application has higher precedence than all other operators
ie: 
```
> show $ sumOfSquares 3 4 + 5
"30"
```

## Resources
 
* [The Purescript book](https://leanpub.com/purescript/read#leanpub-auto-test-early-test-often): Excellent book, not only the content is good, it is a pleasurable read. Will review when I finish it.
* [Learn x in Y minutes: Purescript](https://learnxinyminutes.com/docs/purescript/) Good as a quick reference.
* [Cheatsheet](https://github.com/joshburgess/purescript-cheat-sheet)
