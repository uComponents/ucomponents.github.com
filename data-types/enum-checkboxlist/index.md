---
layout: datatype
title: Enum CheckBoxList
category: Data Types
description: Use an Enum as the data source for a CheckBoxList.
since_version: 
retired_version: 
---

## Prevalue Editor Settings


The Enum can be decorated with optional EnumCheckBoxList attributes to configure how the Text and Value fields are populated, as well as being able to exclude items from the resulting list.

**Enabled** a boolean value to indicate if the item should be included in the list.

**Text** the text to use in the list instead of the Enum item name.

**Value** the value to use in the list instead of the Enum item name.

public enum Example
{
	[EnumCheckBoxList(Enabled=false)]
	Item1,

	[EnumCheckBoxList(Text="Item One")]
	Item2,

	[EnumCheckBoxList(Value="3")]
	Item3,

	[EnumCheckBoxList(Text="Item Four", Value="4")]
	Item4,

	Item5
}

## Content Editor


## uQuery

	Example example = uQuery.GetCurrentNode().GetProperty<Example>("propertyAlias");
