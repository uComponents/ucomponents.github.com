---
layout: datatype
title: Image Point
category: Data Types
description: Place a marker on an image to store an X, Y coordinate value.
since_version: 6.0.0
---

## Prevalue Editor Settings

![Prevalue Editor](PreValueEditor.png)

**Image Property Alias** :  The property alias to to use for the image url source. This can be a property on the same node, or (if on content / media) it can be a property further up the tree hierarachy - the closest property is used. This property can be an image upload, or any datatype that stores a relative url to an image.

**Width** : When specified, this will override the image width.

**Height** : When specified, this will override the image height.

If either a _Width_ or _Height_ is > 0 and the other is set to 0, then the one set to 0 will be calculated from the image dimensions so as to maintain the correct aspect ratio.


## Content Editor

![Content Editor](DataEditor.png)

Image Point allows a marker to be placed on an image and stored as an X,Y coordinate in a CSV string.

Using the hierarachial nature of aquiring the image source allows other data to be associated with any given point.

