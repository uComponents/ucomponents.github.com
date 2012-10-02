---
layout: datatype
title: Auto Complete
since_version: 1.0
---

## Prevalue Editor Settings

![Prevalue Editor](PreValueEditor.jpg)

## Content Editor

![Content Editor 1](DataEditor1.jpg)

![Content Editor 2](DataEditor2.jpg)

## uQuery

	var currentNode = uQuery.GetCurrentNode();
	var colourNodes = uQuery.GetNodesByCsv(currentNode.GetProperty<string>("propertyAlias"));
