---
layout: datatype
title: Creating Maps
category: uMapper
---

Before you can use uMapper, you must create your maps.

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