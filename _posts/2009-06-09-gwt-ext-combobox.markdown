---
author: roundcrisis
comments: true
date: 2009-06-09 08:41:36+00:00
layout: post
slug: gwt-ext-combobox
title: GWT-Ext ComboBox loading from XML
wordpress_id: 277
categories:
- ExtJs
- GWT
tags:
- gwt-ext
---

This is a simple example on how to make a ComboBox in Gwt-Ext to populate with XML.

`HttpProxy proxy = new HttpProxy("xml/combo_data.xml", Connection.GET);`

`final RecordDef recordDef = new RecordDef(new FieldDef[] {
new StringFieldDef("id"),
new StringFieldDef("value") });`

`XmlReader reader = new XmlReader("comboitem", recordDef);`

`final Store store = new Store(proxy, reader);

ComboBox combo = new ComboBox();
combo.setLabel("Combo Label");
combo.setStore(store);
combo.setDisplayField("value");
combo.setMode(ComboBox.REMOTE);
combo.setTypeAhead(true);
this.rootPanel.add(combo);

`

` store.load();
`
And the xml can be seen [here](http://pastebin.com/f6684d7a7)

Hope it helps
