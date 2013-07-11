---
layout: datatype
title: Sub Tabs
category: Data Types
description: Adds a second level of tabs, by hiding specified tabs, and toggling their contents into view based on a series of buttons, or a drop down list.
since_version: 4.0
retired_version: 
---
## Prevalue Editor Settings

![Prevalue Editor](PreValueEditor.jpg)

**Tabs** : the tabs to hide

**Type** : either a drop down list, or series of buttons

**Show Label** : allows hiding the name and description


## Setting

![Setting](Setting.jpg)

Note: this datatype expects to be be only property on a tab - this is because it works by firing the Umbraco click event on the hidden tab, and moving itself to be the first property on that tab - on load it defaults to the first hidden tab, so any original sibling properties would never be displayed.


## Content Editor

Before:
![Before](Before.jpg)

After:
![After](After.jpg)
