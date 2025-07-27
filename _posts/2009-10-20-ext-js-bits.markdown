---
author: roundcrisis
comments: true
date: 2009-10-20 19:00:54+00:00
layout: single
classes: wide
slug: ext-js-bits
title: 'Ext Js bits '
wordpress_id: 415
---

Just some interesting thing I found on the extjs world.

I m only looking at stuff working on ext3.0

In ExtJs the JsonStore has **paramNames** this Object contains 4 properties

    
    {
        start : 'start',  // The parameter name which specifies the start row
        limit : 'limit',  // The parameter name which specifies number of rows to return
        sort : 'sort',    // The parameter name which specifies the column to sort on
        dir : 'dir'       // The parameter name which specifies the sort direction
    }


This properties are the default however they can be changed by using a configuration property or to change globally
it should be changed in the **store** prototype


## Drag and Drop into a grid


Shea Frederick has a very nifty Excel drag and drop into the grid, got the code
and runs in ie7, ie8, ff3.5 and Chrome and you can get it [here](http://www.vinylfox.com/datadrop-drag-grid-data-from-spreadsheet/)
