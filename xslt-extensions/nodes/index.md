---
layout: extension
title: Nodes
category: XSLT Extensions
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Nodes" alias="ucomponents.nodes" />
		...
	</XsltExtensions>

## Methods
Here are available methods:

### GetExpireDate
Gets the expiry date of a node.
_Returns_: Returns the expiry date of a node.

#### Parameters
| Name | Type |
|------|------|
| nodeId | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetExpireDate(nodeId)" />


*****

### GetNodeIdByUrl
Gets the node Id by URL.
_Returns_: Returns the node Id.

#### Parameters
| Name | Type |
|------|------|
| url | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetNodeIdByUrl(url)" />


*****

### GetNodeIdByPathLevel
Gets the node id by path level.
_Returns_: Returns the node id for a given path level.

#### Parameters
| Name | Type |
|------|------|
| path | System.String |
| level | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetNodeIdByPathLevel(path, level)" />


*****

### GetReleaseDate
Gets the release date of a node.
_Returns_: Returns the release date of a node.

#### Parameters
| Name | Type |
|------|------|
| nodeId | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetReleaseDate(nodeId)" />


*****

### GetUniqueId
Gets the unique id of a node.
_Returns_: Returns the unique id of a node.

#### Parameters
| Name | Type |
|------|------|
| nodeId | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetUniqueId(nodeId)" />


*****

### GetXmlNodeByCsv
Gets a list of XML nodes by CSV.
_Returns_: Returns an XPathNodeIterator of the nodes from the CSV list.

#### Parameters
| Name | Type |
|------|------|
| csv | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetXmlNodeByCsv(csv)" />


*****

### GetXmlNodeByCsv
Gets a list of XML nodes by CSV (with an option to persist the order).
_Returns_: Returns an XPathNodeIterator of the nodes from the CSV list.

#### Parameters
| Name | Type |
|------|------|
| csv | System.String |
| persistOrder | System.Boolean |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetXmlNodeByCsv(csv, persistOrder)" />


*****

### GetXmlNodeByPathLevel
Gets the XML node by path level.
_Returns_: Returns an XML node by path level.

#### Parameters
| Name | Type |
|------|------|
| path | System.String |
| level | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetXmlNodeByPathLevel(path, level)" />


*****

### GetXmlNodeByUrl
Gets the XML node by URL.
_Returns_: Returns the XML for the node.

#### Parameters
| Name | Type |
|------|------|
| url | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetXmlNodeByUrl(url)" />


*****

### GetXPathQuery
Gets the XPath query.
_Returns_: Returns an XPath query for the specified URL.

#### Parameters
| Name | Type |
|------|------|
| url | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetXPathQuery(url)" />


*****

