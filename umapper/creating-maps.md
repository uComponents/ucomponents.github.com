---
layout: datatype
title: Creating Maps
category: uMapper
---

Before you can use uMapper, you must create your maps.  You do this by calling `uMapper.CreateMap<YourModel>()` and then using the fluent interface to map any properties which uMapper can't figure out.  There are several different ways to map properties, and these are outline below.
{% highlight c# %}
class Artist
{
    public string Name { get; set; }
}

uMapper.CreateMap<Artist>();

// If necessary, override the document type alias:
uMapper.CreateMap<Artist>("LeArtiste");
{% endhighlight %} 


## Default property mapping ##
This refers to properties which are common to all nodes, such as `Id` and `Name`.  You do not need to include these properties when querying.  In a situation where the property name on your model does not correlate with the node property name, or you wish to run a mapping on the property (such as `Trim()`), you can use the `DefaultProperty()` method:
{% highlight c# %}
uMapper.CreateMap<Artist>()
    .DefaultProperty(
        artist => artist.Name,
        node => node.Name,
        p => p.Trim()
        );
{% endhighlight %} 

## Basic property mapping ##
This refers to properties which you've defined in your document type.  You do not need to include these properties when querying.  uMapper will automatically map any properties which satisfy a case-insensitive comparison, but if they differ you can just reroute a property:
{% highlight c# %}
class Artist
{
    public int MemberCount { get; set; }
    public IEnumerable<string> Tags { get; set; }
}

uMapper.CreateMap<Artist>()
    .BasicProperty(
        artist => artist.MemberCount, // the model property
        "numberOfProperties" // the property alias
        );
{% endhighlight %} 
If you want to apply your own mapping to the property, use this overload:
{% highlight c# %}
uMapper.CreateMap<Artist>()
    .BasicProperty<string>( // ensures a string will be passed into your mapping
        artist => artist.Tags,
        p => p.Split(',').Select(tag => tag.Trim()),
        "myTags" // optional property alias
        );
{% endhighlight %} 

## Single relationship ##
These are properties which refer to another model (i.e. mapped node), and as such need to be included when querying.  They can either be an `int?` or a `TModel`.  If no corresponding property is found on the node, this will contain the closest ancestor which can map to `TModel`.  As expected there are a few ways to customise this mapping:
{% highlight c# %}
class City
{
    public string Name { get; set; }
}

class Artist
{
    public City Origin { get; set; } // single relationship
}

uMapper.CreateMap<City>();
uMapper.CreateMap<Artist>()
    .SingleProperty(
        artist => artist.Origin,
        "placeOfOrigin" // set the property alias if necessary
        );
        
uMapper.CreateMap<Artist>()
    .SingleProperty(
        artist => artist.Origin,
        id => {
            // 'id' is the ID of the artist node being mapped.
            
            var childCities = new Node(id).GetChildNodesByType("City");
            
            return childCities.Any() 
                ? childCities.First().Id 
                : (int?)null; // must return null if not found
        });
        
uMapper.CreateMap<Artist>()
    .SingleProperty<string>(
        artist => artist.Origin,
        p => 
        {
            // 'p' is the property as a string
            var matchingCities = uQuery.GetNodesByType("City").Where(x => x.Name.Contains(p));
            
            return matchingCities.Any()
                ? matchingCities.First().Id
                : (int?)null; // not found
        },
        "placeOfOrigin" // optional
        );
{% endhighlight %} 

## Collection relationship ##
These are properties which refer to a collection of other models, and must be included when querying.  They can either be `IEnumerable<int>` or `IEnumerable<TModel>`, or a type which implements `IEnumerable<T>` and takes `IEnumerable<T>` in a single argument constructor (such as `List<T>`). If no corresponding property is found on the node, this will contain all descendants which can map to `TModel`.
{% highlight c# %}
class Gig
{
    public string Name { get; set; }
}

class Artist
{
    public IEnumerable<Gig> Gigs { get; set; }
}

uMapper.CreateMap<Gig>();

// Set the property alias.  This should be a CSV of node IDs (e.g. Multi-Node Tree Picker)
uMapper.CreateMap<Artist>()
    .CollectionProperty(
        artist => artist.Gigs,
        "performances"
        );
        
// Map the IDs based on the ID of the artist
uMapper.CreateMap<Artist>()
    .CollectionProperty(
        artist => artist.Gigs,
        id => new Node(id).GetChildNodesByType("Gig").Select(n => n.Id) // Just get compatible children
        );
        
// Map the IDs from a property value
uMapper.CreateMap<Artist>()
    .CollectionProperty<string>(
        artist => artist.Gigs,
        p => uQuery.GetNodesByType("Gig").Where(x => x.Name.Contains(p)).Select(n => n.Id),
        "performances" // optional property alias override
        );
{% endhighlight %} 

## Custom relationship ##
Sometimes you just want total domination over your property mappings.
{% highlight c# %}
class Review // not mapped to a document type - just a POCO in the wild
{
    public string Author { get; set; }
    public string BodyHtml { get; set; }
}

class Artist
{
    public IEnumerable<Review> Reviews { get; set; }
}

// Method to map property - conforms to CustomPropertyMapping delegate signature
IEnumerable<Review> MapArtistReviews(int id, string[] paths, ICacheProvider cache)
{
    var node = new Node(id);

    // The reviews are a DataTypeGrid (a data type from uComponents)
    var reviewsXml = node.GetProperty<string>("reviews");
    var reviews = new List<Review>();

    // parse XML for reviews and tadaaaa!

    return reviews;
}

uMapper.CreateMap<Artist>()
    .CustomProperty(
	artist => artist.Reviews,
        MapArtistReviews,
        false, // this property does not require a specific include when querying
        true // allow the reviews collection to be cached by reference
        );
{% endhighlight %} 

## Removing the mapping for a property ##
`uMapper.CreateMap<Artist>().RemoveMappingForProperty(x => x.Name);`
