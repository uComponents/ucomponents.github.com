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
* [GetXmlDocumentByUrl](#getxmldocumentbyurl)
* [Parse](#parse)
* [ParseXml](#parsexml)
* [ParseXhtml](#parsexhtml)
* [RandomChildNode](#randomchildnode)
* [RandomNode](#randomnode)
* [RandomSort](#randomsort)
* [RandomSort](#randomsort)
* [Split](#split)
* [Split](#split)
* [Split](#split)

*****

### FilterNodes
Filters the node-set with the specified XPath.
_Returns_: Returns an XPathNodeIterator of the filtered node-set.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeset | ```System.Xml.XPath.XPathNodeIterator``` | |
| xpath | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:FilterNodes(nodeset, xpath)" />


*****

### GetXmlDocumentByUrl
Gets the XML document by URL.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| url | ```System.String``` | |
| cacheInSeconds | ```System.Int32``` | |
| isGzipped | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:GetXmlDocumentByUrl(url, cacheInSeconds, isGzipped)" />


*****

### Parse
Parses the specified XML string.
_Returns_: Returns an XPathNodeIterator of the XML string.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| xml | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:Parse(xml)" />


*****

### ParseXml
Parses the specified XML string.
_Returns_: Returns an XPathNodeIterator of the XML string.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| xml | ```System.String``` | |
| xpath | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:ParseXml(xml, xpath)" />


*****

### ParseXhtml
Parses the specified XHTML string.
_Returns_: Returns an XPathNodeIterator of the XHTML string.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| xhtml | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:ParseXhtml(xhtml)" />


*****

### RandomChildNode
Returns a random child node from the parent node.
_Returns_: Returns an XPathNodeIterator of a random child node from the parent node.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| node | ```System.Xml.XPath.XPathNavigator``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:RandomChildNode(node)" />


*****

### RandomNode
Returns a random node from the node-set.
_Returns_: Returns an System.Xml.XPath.XPathNodeIterator of a random node from the node-set.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeset | ```System.Xml.XPath.XPathNodeIterator``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:RandomNode(nodeset)" />


*****

### RandomSort
Randomizes the sort order of the specified nodeset.
_Returns_: Returns the nodeset with a random sort order.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| node | ```System.Xml.XPath.XPathNavigator``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:RandomSort(node)" />


*****

### RandomSort
Randomizes the sort order of the specified nodeset, limited to a specified number.
_Returns_: Returns the nodeset with a random sort order.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| node | ```System.Xml.XPath.XPathNavigator``` | |
| count | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:RandomSort(node, count)" />


*****

### Split
Splits the specified delimited string into an XPathNodeIterator.
_Returns_: Returns an System.Xml.XPath.XPathNodeIterator representation of the delimited string data.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| data | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:Split(data)" />


*****

### Split
Splits the specified delimited string into an XPathNodeIterator.
_Returns_: Returns an System.Xml.XPath.XPathNodeIterator representation of the delimited string data.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| data | ```System.String``` | |
| separator | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:Split(data, separator)" />


*****

### Split
Splits the specified delimited string into an XPathNodeIterator.
_Returns_: Returns an System.Xml.XPath.XPathNodeIterator representation of the delimited string data.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| data | ```System.String``` | |
| separator | ```System.String``` | |
| rootName | ```System.String``` | |
| elementName | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.xml:Split(data, separator, rootName, elementName)" />


*****

