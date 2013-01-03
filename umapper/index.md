---
layout: datatype
title: uMapper
category: root
since_version: 5.1.0
---

uMapper lets .NET developers map & query nodes as strongly typed objects with minimal configuration.  It does its best to map the properties and relationships of a node to an object by name, but features a fluent interface for manual configuration in the much the same way AutoMapper does.

I've put together an [example project](https://bitbucket.org/JamesDiacono/umapperexample/src) with Umbraco 4.9.0 which shows example usage of uMapper. A SQLCE database is included as a file, and the username and password for the Umbraco back office are both "admin".

## Usage (minimal configuration) ##
1. Add a reference to uComponents.Mapping.dll in your web project (this should already be added if you used NuGet to install uComponents).

2. Create your document types in Umbraco:
![Example tree](ExampleTree.png)
Make sure you use CSV as the data format for any multi-node pickers you use.

3. Create your corresponding models as .NET classes in your project, naming the classes the same as the document type aliases:
{% highlight c# %}
public class Artist
{
    public string Name { get; set; }
    public IEnumerable<Genre> Genres { get; set; } // You can also use List<T>
}
{% endhighlight %} 

4. Derive from `ApplicationStartupHandler` and create your maps (these must be created before you start mapping nodes, or uMapper doesn't know which classes to map to).  Now is also a good time to enable caching (which uses the `HttpContext.Current.Cache`):
{% highlight c# %}
using uComponents.Mapping;
using umbraco.businesslogic;

public class ExampleStartupHandler : ApplicationStartupHandler
{
    public ExampleStartupHandler()
    {
        uMapper.CreateMap<Site>();
        uMapper.CreateMap<Genre>();
        uMapper.CreateMap<Artist>();

	uMapper.CachingEnabled = true;
    }
}
{% endhighlight %} 

5. Get some nice data!
{% highlight c# %}
public partial class Site : System.Web.UI.MasterPage
{
    protected Homepage Model { get; set; }
    protected IEnumerable<Artist> Artists { get; set; }
    protected IEnumerable<Genre> Genres { get; set; }

    protected void Page_Load(object sender, EventArgs e)
    {
        this.Model = uMapper.GetCurrent<Homepage>();

        this.Artists = uMapper.GetAll<Artist>
            .OrderBy(artist => artist.Name);
            
        this.Genres = uMapper.GetAll<Genre>();
		
        var featuredGenre = uMapper.Find<Genre>(1234); // node ID is 1234
    }
}
{% endhighlight %}