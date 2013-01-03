---
layout: datatype
title: Querying
category: uMapper
---

## Shorthand ##
{% highlight c# %}
// By default, all relationships are included in a shorthand query:
var fatArtist = uMapper.GetSingle<Artist>(1063); // fatArtist.Genres.Count == 3

// This can get very expensive very fast.  You can exclude all relationships
// by specifying the optional parameter:
var skinnyArtist = uMapper.GetSingle<Artist>(1063, false); // skinnyArtist.Genres == null

// If performance matters to you, I would advise against using shorthand.

{% endhighlight %}

## Longhand ##
Calling the `uMapper.Query<TDestination>()` methods gets you a fluent interface to 'query' nodes.
I say 'query' because it doesn't implement `IQueryable` (probably never will).
Enumerating the query gives you back all nodes which can be mapped to `TDestination` (which means
models which inherit from `TDestination` will be included).
If you hunger for more query methods, you can write your own extension methods for `INodeQuery<TDestination>`.
{% highlight c# %}
// Maps the current node
var a = uMapper.Query<Artist>().Current();
    
// Maps a node by ID (returns null if it doesn't exist)
var b = uMapper.Query<Artist>().Find(1234);
    
// Maps many nodes
var c = uMapper.Query<Artist>().Many(new[] { 1111, 2222, 3333 });
    
// Maps all nodes which can be mapped to 'Artist'
var d = uMapper.Query<Artist>().ToList();
    
// Maps all nodes which were explicitly mapped to 'Artist'
var e = uMapper.Query<Artist>()
    .Explicit()
    .ToList();

// Maps all artist names
var f = uMapper.Query<Artist>()
    .SelectProperty(artist => artist.Name)
    .ToList();

// Map all artists with short names
var g = uMapper.Query<Artist>()
    .WhereProperty(
        artist => artist.Name,
        name => name.Length < 5
        )
    .ToList();

{% endhighlight %}
#### Querying with paths ####
{% highlight c# %}
var homepage = uMapper.Query<Homepage>()
    .Include(x => x.Genres) // Single level path
    .Include(x => x.Artists.Select(y => y.Genres)) // Syntax for multi-level paths
    .Current(); // Maps the current node

    homepage.Genres // populated
    homepage.FeaturedArtist // null, as it was not included
    homepage.Artists // populated
    homepage.Artists.First().Genres // populated
    
// You can also use string paths (as deep as you like):
var otherHomepage = uMapper.Query<Homepage>()
    .Include("Artists.Genres")
    .Current();
{% endhighlight %}  