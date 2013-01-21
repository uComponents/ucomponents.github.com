---
layout: datatype
title: Text Image
category: Data Types
since_version: 2.1.0
retired_version: 5.3.1
---

The TextImage datatype allows for generation of an image of text based on settings (color, background, font, size, position, etc..)

It allows the use of server fonts as well as a custom font (TTF file)

It appears on doctypes as a standard textbox, but generates an image file on save (displayed in a preview)

## Prevalue Editor Settings

![Prevalue Editor](PreValueEditor.jpg)

## Content Editor

![Content Editor](DataEditor.jpg)

## XSLT Example

	<img src="{$textImage/TextImage/Url}" alt="{$textImage/TextImage/Text}"/>
