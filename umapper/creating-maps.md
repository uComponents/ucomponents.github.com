---
layout: datatype
title: Creating Maps
category: uMapper
---

Before you can use uMapper, you must create your maps.  You do this by calling `uMapper.CreateMap<YourModel>()` and then using the fluent interface to map any properties which uMapper can't figure out.  There are several different ways to map properties, and these are outline below.

## Default property mapping ##
This refers to properties which are common to all nodes, such as `Id` and `Name`.   In a situation where the property name on your model does not correlate with the node property name, or you wish to run a mapping on the property (such as `Trim()`), you can use the `DefaultProperty()` method:
{% highlight c# %}
uMapper.CreateMap<Artist>()
    .DefaultProperty(
        artist => artist.Name,
        node => node.Name,
        p => p.Trim()
        );
{% endhighlight %} 

## Basic property mapping ##
This refers to properties which you've defined in your document type.  uMapper will automatically map any properties which satisfy a case-insensitive comparison, but if they differ you can just reroute a property:
{% highlight c# %}
uMapper.CreateMap<Artist>()
    .BasicProperty(
        artist => artist.MemberCount, // the model property
        "numberOfProperties" // the property alias
        );
{% endhighlight %} 
If you want to apply your own mapping to the property, use this overload:
{% highlight c# %}
uMapper.CreateMap<Artist>()
    .BasicProperty<string>( // the type parameter is the system type passed into your mapping
        artist => artist.Tags, // the Tags property is IEnumerable<string>
        p => p.Split(',').Select(tag => tag.Trim()),
        "myTags" // optional property alias
        );
{% endhighlight %} 


## Default mapping behaviour for model property types ##
* System types and enums are mapped via `Node.GetProperty<TDestination>()` (including nullables)
* A collection of `TDestination` (without a corresponding node property) will map from all descendant nodes which map to `TDestination`.
* A `TDestination` (without a corresponding node property) will map the closest ancestor node which maps to `TDestination`.
* Using a collection of `int` will map node IDs rather than models.
* Properties with the same name as properties on `umbraco.NodeFactory.Node` will map automagically.
* Custom collections which implement `IEnumerable<>` and take a single argument constructor of `IEnumerable<>` can be used.

## Overriding the node type alias ##
`uMapper.CreateMap<Artist>("SomeNodeTypeAlias");`
## Overriding the default property mapping ##
{% highlight c# %}
uMapper.CreateMap<Artist>()
    .ForProperty(
        x => x.Name, // Choose the model property
        (node, paths) => node.GetProperty<string>("AlternateName"), // Specify a custom mapping
        false // Decide if this mapping counts as a relationship
        );
{% endhighlight %} 
## Removing the default mapping for a property ##
`uMapper.CreateMap<Artist>().RemoveMappingForProperty(x => x.Name);`
