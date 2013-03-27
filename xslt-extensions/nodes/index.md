---
layout: extension
title: Nodes
category: XSLT Extensions
since_version: 2.1.0
---

## Activation

### Version 6.0.0 (and above)
As of uComponents v6.0.0 all XSLT extensions are automatically registered with Umbraco. Newly created XSLT files (in the back-office) will already contain the appropriate namespaces.  For existing XSLT files, you will still need to add the `ucomponents.nodes` namespace.

### Prior to version 6.0.0

Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Nodes" alias="ucomponents.nodes" />
		...
	</XsltExtensions>

*****

## Methods
Here are available methods in the ```Nodes``` library:

* [GetExpireDate](#getexpiredate)
* [GetNodeIdByUrl](#getnodeidbyurl)
* [GetNodeIdByPathLevel](#getnodeidbypathlevel)
* [GetReleaseDate](#getreleasedate)
* [GetUniqueId](#getuniqueid)
* [GetXmlNodeByCsv](#getxmlnodebycsv)
* [GetXmlNodeByPathLevel](#getxmlnodebypathlevel)
* [GetXmlNodeByUrl](#getxmlnodebyurl)

*****

### GetExpireDate
Gets the expiry date of a node; e.g. when the content is scheduled to be unpublished.<br>
_Returns_: Returns the expiry date of a node.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetExpireDate($currentPage/@id)" />


*****

### GetNodeIdByUrl
Gets the node Id by URL.<br>
_Returns_: Returns the node Id for a given URL.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| url | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetNodeIdByUrl('/nice-url/')" />


*****

### GetNodeIdByPathLevel
Gets the node id by path level.<br>
_Returns_: Returns the node id for a given path level.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |
| level | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetNodeIdByPathLevel('-1,1059,1083,1085', 1)" />


*****

### GetReleaseDate
Gets the release date of a node (to be published).<br>
_Returns_: Returns the release date of a node.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetReleaseDate(1099)" />


*****

### GetUniqueId
Gets the unique id (`System.Guid`) of a node.<br>
_Returns_: Returns the unique id of a node.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.nodes:GetUniqueId($currentPage/@id)" />


*****

### GetXmlNodeByCsv
Gets a list of XML nodes by CSV (with an option to persist the order).<br>
_Returns_: Returns an `XPathNodeIterator` of the nodes from the CSV list.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| csv | ```System.String``` | |
| persistOrder | ```System.Boolean``` | _(optional - defaults to ```false```)_ |

#### XSLT Example

	<ul>
		<xsl:for-each select="ucomponents.nodes:GetXmlNodeByCsv('1085,1086,1087,1088', false())">
			<li>
				<a href="{umbraco.library:NiceUrl(@id)}">
					<xsl:value-of select="@nodeName" />
				</a>
			</li>
		</xsl:for-each>
	</ul>


*****

### GetXmlNodeByPathLevel
Gets the XML node by path level.<br>
_Returns_: Returns an XML node by path level.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |
| level | ```System.Int32``` | |

#### XSLT Example

	<xsl:variable name="homepage" select="ucomponents.nodes:GetXmlNodeByPathLevel($currentPage/@path, 1)" />
	<xsl:value-of select="$homepage/@nodeName" />


*****

### GetXmlNodeByUrl
Gets the XML node by URL.<br>
_Returns_: Returns the XML for the node.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| url | ```System.String``` | |

#### XSLT Example

	<xsl:variable name="node" select="ucomponents.nodes:GetXmlNodeByUrl('/nice-url/')" />
	<xsl:value-of select="$node/@nodeName" />


*****


