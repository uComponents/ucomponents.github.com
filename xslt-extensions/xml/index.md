---
layout: extension
title: Xml
category: XSLT Extensions
since_version: 1.0
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Xml" alias="ucomponents.xml" />
		...
	</XsltExtensions>

*****

## Methods
Here are available methods in the ```Xml``` library:

* [FilterNodes](#filternodes)
* [GetXmlDocument](#getxmldocument)
* [GetXmlDocumentByUrl](#getxmldocumentbyurl)
* [Parse](#parse)
* [ParseXml](#parsexml)
* [ParseXhtml](#parsexhtml)
* [RandomChildNode](#randomchildnode)
* [RandomNode](#randomnode)
* [RandomSort](#randomsort)
* [Split](#split)

*****

### FilterNodes
The ```FilterNodes``` method is used to further filter a node-set with an XPath expression (string).

Typically you could perform these filters in XSLT directly, however there are situations where you may want to build an XPath expression dynamically, which can lead to complexities - especially for those new to developing with XSLT.

_Returns_: Returns an XPathNodeIterator of the filtered node-set.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeset | ```System.Xml.XPath.XPathNodeIterator``` | |
| xpath | ```System.String``` | |

#### XSLT Example

	<!-- Filter all the descendant node of the $currentPage for those that contain a 'bodyText' element (with normalized space, e.g. not empty) -->
	<xsl:for-each select="ucomponents.xml:FilterNodes($currentPage, '//*[@isDoc and bodyText[normalize-space()]]')">
		<xsl:value-of select="@nodeName" />
	</xsl:for-each>

*****

### GetXmlDocument
Get an XML document by local file path.

This method makes a call to the ```umbraco.library:GetXmlDocument()``` method, with the addition of the ```cacheInSeconds``` parameter - which will cache the XML document for a specified number of seconds.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |
| relative | ```System.Boolean``` | |
| cacheInSeconds | ```System.Int32``` | |

#### XSLT Example

	<xsl:copy-of select="ucomponents.xml:GetXmlDocument('~/App_Data/data.xml', true(), 600)" />

*****

### GetXmlDocumentByUrl
Gets an XML document by URL.

This method is the same as the ```umbraco.library:GetXmlDocumentByUrl()``` method, with the addition of the ```isGzipped``` parameter - which is able to decompress Gzipped XML responses.

If ```isGzipped``` is set to ```false()```, then the ```umbraco.library:GetXmlDocumentByUrl(url, cacheInSeconds)``` is called by default.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| url | ```System.String``` | |
| cacheInSeconds | ```System.Int32``` | |
| isGzipped | ```System.Boolean``` | |

#### XSLT Example

	<xsl:copy-of select="ucomponents.xml:GetXmlDocumentByUrl('http://google.com/sitemap.xml', 600, false())" />

*****

### Parse

The Parse method is used for those situations where you have an XML string and need to convert it into a node-set (e.g. XML document, or rather an XPathNodeIterator).

Internally this method calls [```ParseXml```](#parsexml) with the the ```xpath``` parameter set to the root ("/").

_Returns_: Returns an XPathNodeIterator of the XML string.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| xml | ```System.String``` | |

#### XSLT Example

	<xsl:copy-of select="ucomponents.xml:Parse('<root><node>Value 1</node><node>Value 2</node></root>')" />

*****

### ParseXml
Parses the specified XML string.<br>
_Returns_: Returns an XPathNodeIterator of the XML string.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| xml | ```System.String``` | |
| xpath | ```System.String``` | The XPath expression to return the node-set. |

#### XSLT Example

	<xsl:copy-of select="ucomponents.xml:ParseXml('<root><node>Value 1</node><node>Value 2</node></root>', '//node')" />

*****

### ParseXhtml
Parses the specified XHTML string.<br>
_Returns_: Returns an XPathNodeIterator of the XHTML string.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| xhtml | ```System.String``` | |

#### XSLT Example

	<!-- Parse the HTML content of the 'bodyText' property into workable XML -->
	<xsl:copy-of select="ucomponents.xml:ParseXhtml($currentPage/bodyText)" />

*****

### RandomChildNode
The ```RandomChildNode``` method is a compliment to [```RandomNode```](#randomnode), where instead of passing a node-set to select a random node from, you pass it a parent node, of which one of the child nodes is returned at random.

_Returns_: Returns an XPathNodeIterator of a random child node from the parent node.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| node | ```System.Xml.XPath.XPathNavigator``` | |

#### XSLT Example

	<!-- Return a random property from the $currentPage node -->
	<xsl:value-of select="ucomponents.xml:RandomChildNode($currentPage)" />

*****

### RandomNode
The ```RandomNode``` method accepts a node-set and returns a single node selected at random.

It is important to note that the input node-set must be a collection of nodes, (a result tree fragment) and not a parent node.  For example, calling RandomNode($currentPage) would return itself - as there is only a single node to choose from!

_Returns_: Returns an System.Xml.XPath.XPathNodeIterator of a random node from the node-set.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeset | ```System.Xml.XPath.XPathNodeIterator``` | |

#### XSLT Example

	<!-- Return a random content page from the $currentPage -->
	<xsl:copy-of select="ucomponents.xml:RandomNode($currentPage/*[@isDoc])" />

*****

### RandomSort
Randomizes the sort order of the specified node-set, (can be limited to a specified number of nodes).<br>
_Returns_: Returns the nodeset with a random sort order.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| node | ```System.Xml.XPath.XPathNavigator``` | |
| count | ```System.Int32``` | _(optional)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:RandomSort($currentPage/*[@isDoc], 5)" />

*****

### Split
Splits the specified delimited string into an XPathNodeIterator.<br>
_Returns_: Returns an System.Xml.XPath.XPathNodeIterator representation of the delimited string data.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| data | ```System.String``` | A string delimited list, e.g. CSV |
| separator | ```System.String``` | _(optional - defaults to a comma ```,```)_ |
| rootName | ```System.String``` | _(optional - defaults to 'values')_ |
| elementName | ```System.String``` | _(optional - defaults to 'value')_ |

#### XSLT Example

	<!-- Take a comma-separated list, split it and display as HTML list. -->
	<ul>
		<xsl:for-each select="ucomponents.xml:Split('hello,world,foo,bar')//values">
			<li>
				<xsl:value-of select="text()" />
			</li>
		</xsl:for-each>
	</ul>

*****

