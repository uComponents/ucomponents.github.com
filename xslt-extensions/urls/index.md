---
layout: extension
title: Urls
category: XSLT Extensions
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Urls" alias="ucomponents.urls" />
		...
	</XsltExtensions>

## Methods
Here are available methods:

### AppendOrUpdateQueryString
Appends or updates a query string value to the current Url
_Returns_: The updated Url

#### Parameters
| Name | Type |
|------|------|
| key | System.String |
| value | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:AppendOrUpdateQueryString(key, value)" />


*****

### AppendOrUpdateQueryString
Appends or updates a query string value to supplied Url
_Returns_: The updated Url

#### Parameters
| Name | Type |
|------|------|
| url | System.String |
| key | System.String |
| value | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:AppendOrUpdateQueryString(url, key, value)" />


*****

### FormatUrl
Formats the URL - replacing characters in the string to make a 'safe' URL.
_Returns_: Returns a 'safe' URL, removing illegal characters.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:FormatUrl(input)" />


*****

### NiceUrl
Returns a nicely formated Url for a given node.
_Returns_: The NiceUrl for the node id.

#### Parameters
| Name | Type |
|------|------|
| nodeId | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:NiceUrl(nodeId)" />


*****

### NiceUrl
Returns a nicely formated Url for a given node and alternative template.
_Returns_: The NiceUrl for the node id.

#### Parameters
| Name | Type |
|------|------|
| nodeId | System.Int32 |
| altTemplateAlias | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:NiceUrl(nodeId, altTemplateAlias)" />


*****

### NiceUrl
Returns a nicely formated Url for a given node and alternative template.
_Returns_: The NiceUrl for the node id.

#### Parameters
| Name | Type |
|------|------|
| nodeId | System.Int32 |
| altTemplateAlias | System.String |
| useQueryString | System.Boolean |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:NiceUrl(nodeId, altTemplateAlias, useQueryString)" />


*****

### GetHostName
Gets the hostname of the node Id.
_Returns_: Returns the hostname for the node Id.

#### Parameters
| Name | Type |
|------|------|
| nodeId | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:GetHostName(nodeId)" />


*****

### GetNodeIdByUrl
Gets the node Id by URL.
_Returns_: Returns the node Id.

#### Parameters
| Name | Type |
|------|------|
| url | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:GetNodeIdByUrl(url)" />


*****

### GetTextByUrl
Gets the text by URL.
_Returns_: Returns the text (System.String) from a given URL.

#### Parameters
| Name | Type |
|------|------|
| url | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:GetTextByUrl(url)" />


*****

### GetXmlNodeByUrl
Gets the XML node by URL.
_Returns_: Returns the XML for the node.

#### Parameters
| Name | Type |
|------|------|
| url | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:GetXmlNodeByUrl(url)" />


*****

### GuessNiceUrl
Guesses the NiceUrl based on the node id.
_Returns_: Returns a guestimate of the NiceUrl for a node id.

#### Parameters
| Name | Type |
|------|------|
| nodeId | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:GuessNiceUrl(nodeId)" />


*****

### ConstructQueryString
Constructs a NameValueCollection into a query string.
_Returns_: A key/value structured query string, delimited by the specified String

#### Parameters
| Name | Type |
|------|------|
| parameters | System.Collections.Specialized.NameValueCollection |
| delimiter | System.String |
| omitEmpty | System.Boolean |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:ConstructQueryString(parameters, delimiter, omitEmpty)" />


*****

### GetNiceUrl
Gets the NiceUrl.
_Returns_: Returns the NiceUrl for the node id.

#### Parameters
| Name | Type |
|------|------|
| nodeId | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:GetNiceUrl(nodeId)" />


*****

### OnBeforeNiceUrlGenerated
Dispatches a BeforeNiceUrlGenerated event.

#### Parameters
| Name | Type |
|------|------|
| nodeId | System.Int32@ |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:OnBeforeNiceUrlGenerated(nodeId)" />


*****

### OnAfterNiceUrlGenerated
Dispatches an AfterNiceUrlGenerated event.

#### Parameters
| Name | Type |
|------|------|
| nodeId | System.Int32@ |
| url | System.String@ |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:OnAfterNiceUrlGenerated(nodeId, url)" />


*****

