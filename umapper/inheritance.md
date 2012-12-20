---
layout: datatype
title: Inheritance
category: uMapper
---

{% highlight c# %}
// You can structure your model classes to reflect the inheritance
// in the document type tree.

// Create your base map first.
uMapper.CreateMap<Artist>() // maps from "Artist" node type
	.ForProperty(x => x.Name, (node, paths) => "Hello", false);

// Create your derived maps later.
//
// The model SoloArtist inherits from Artist.
//
// This creates a map from the "SoloArtist" node type, 
// which inherits from the "Artist" node type.
uMapper.CreateMap<SoloArtist>(); 

var soloArtist = uMapper.GetSingle<SoloArtist>(1061);
// soloArtist.Name == "Hello"

// You can map a node to a base model.
var artist = uMapper.Query<Artist>().Single(1061); 

// And cast it back: 
(artist as SoloArtist).Name // "Hello"

// Or get every node which maps to a base model:
List<Artist> allArtists = uMapper.Query<Artist>(); // contains Artist and SoloArtist items

// Or get every node which is explicitly mapped to the base model:
List<Artist> baseArtists = uMapper.Query<Artist>().Explicit(); // contains only Artist
{% endhighlight %} 