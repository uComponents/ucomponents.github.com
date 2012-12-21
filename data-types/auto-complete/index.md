---
layout: datatype
title: Auto Complete
category: Data Types
description: This data-type provides a way to select multiple nodes (either Content, Media or Members) using an auto-complete interface.
since_version: 1.0
retired_version: 5.2
---

## Prevalue Editor Settings

![Prevalue Editor](PreValueEditor.jpg)

## Content Editor

![Content Editor 1](DataEditor1.jpg)

![Content Editor 2](DataEditor2.jpg)

## uQuery

	var currentNode = uQuery.GetCurrentNode();
	var colourNodes = uQuery.GetNodesByCsv(currentNode.GetProperty<string>("propertyAlias"));
