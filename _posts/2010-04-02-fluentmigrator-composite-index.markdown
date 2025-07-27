---
author: roundcrisis
comments: true
date: 2010-04-02 10:19:22+00:00
layout: single
classes: wide
slug: fluentmigrator-composite-index
title: FluentMigrator Composite Index
wordpress_id: 538
categories:
- .net
- NHibernate
tags:
- fluentmigrator
- NHibernate
---

[Fluentmigrator ](http://github.com/schambers/fluentmigrator/)is a really nice migration tool that allows you to tear your database up and down keeping version, please visit the project page for more info.

Anyway, the other day I had to create a composite index, and I didnt know how,  the way to do that is:

Create.Index("Name_of_the_index_String").OnTable("Name_of_the_Table_String")
.OnColumn("Column_Name_string").Ascending()
.OnColumn("Other_Column_Name_string").Ascending();

Looks kinda obvious no? but what threw me off at the time is that I was looking at the possible operations after OnColumn and there was nothign obvious there,

[![FluentMigrator Create Index Column Intellisense](http://roundcrisis.files.wordpress.com/2010/04/fm_index1.png)](http://roundcrisis.files.wordpress.com/2010/04/fm_index1.png)

then  I looked at the Sql documentation for CREATE INDEX



    
    CREATE [ UNIQUE ] [ CLUSTERED | NONCLUSTERED ] INDEX index_name
        ON <object> ( column [ ASC | DESC ] [ ,...n ] )
        [ INCLUDE ( column_name [ ,...n ] ) ]
        [ WHERE <filter_predicate> ]
        [ WITH ( <relational_index_option> [ ,...n ] ) ]


The solution was (kind of) there, you could do more columns after you specify the sorting direction. Perhaps it's  obvious but it took me a while to figure out. It was logical however not obvious.

Also on composite, before I created an index I thought about using composite keys, J.Miller has a post [here ](http://codebetter.com/blogs/jeremy.miller/archive/2007/02/01/Composite-keys-are-evil.aspx)on why that is not really a good idea ( have a look at the comments in particular). For me, it boils down to:



	
  * Maybe something that has meaning now, wont necessarily have the same meaning in the future

	
  * It's harder to manage composite keys that it is to manage surrogate keys


There are more reasons for and against surrogate keys, but this was what was suitable to me at the time

Cheers
