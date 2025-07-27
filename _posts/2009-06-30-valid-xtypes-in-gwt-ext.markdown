---
author: roundcrisis
comments: true
date: 2009-06-30 11:19:11+00:00
layout: single
classes: wide
slug: valid-xtypes-in-gwt-ext
title: Valid xtypes in GWT-Ext
wordpress_id: 324
categories:
- gwt-ext
tags:
- gwt-ext
---

Say you have a panel, that contains a form and you want to get the values for the fields of that form, one way to go on about it is to use findByType():

    Find a component under this container at any level by xtype.
    

    

**Parameters:**
    `xtype` - the components xtype
**Returns:**
    an array of components
this is all well and good, however the available xtypes, what are those?

A bit of magic string here?,  what are the available xtypes?

You can find a list below:
`
* xtype            Class
* -------------    ------------------
* box              BoxComponent
* button           Button
* colorpalette     ColorPalette
* component        Component
* container        Container
* cycle            CycleButton
* dataview         DataView
* datepicker       DatePicker
* editor           Editor
* editorgrid       EditorGridPanel
* grid             GridPanel
* paging           PagingToolbar
* panel            Panel
* progress         ProgressBar
* splitbutton      SplitButton
* tabpanel         TabPanel
* treepanel        TreePanel
* viewport         ViewPort
* window           Window
*
`

` `

`* Toolbar components
* ---------------------------------------
* toolbar          Toolbar
*
* Form components
* ---------------------------------------
* checkbox         Checkbox
* combo            ComboBox
* datefield        DateField
* field            Field
* fieldset         FieldSet
* form             FormPanel
* hidden           Hidden
* htmleditor       HtmlEditor
* numberfield      NumberField
* radio            Radio
* textarea         TextArea
* textfield        TextField
* timefield        TimeField `

This list is available from the** Component** class in the package **com.gwtext.client.widgets;**

As a cleaner way to deal with this I created an Enum to work with this information.

Hope it saves you 10min.
