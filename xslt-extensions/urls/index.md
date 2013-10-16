---
layout: extension
title: Urls
category: XSLT Extensions
since_version: 2.0
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Urls" alias="ucomponents.urls" />
		...
	</XsltExtensions>

*****

## Methods
Here are available methods in the `Urls` library:

* [AddAltTemplate](#addalttemplate)
* [AppendOrUpdateQueryString](#appendorupdatequerystring)
* [FormatUrl](#formaturl)
* [GetHostName](#gethostname)
* [GetNodeIdByUrl](#getnodeidbyurl)
* [GetTextByUrl](#gettextbyurl)
* [GetXmlNodeByUrl](#getxmlnodebyurl)
* [GuessNiceUrl](#guessniceurl)
* [NiceUrl](#niceurl)

## Events
Here are available events in the `Urls` library:

* [OnBeforeNiceUrlGenerated](#onbeforeniceurlgenerated)
* [OnAfterNiceUrlGenerated](#onafterniceurlgenerated)

*****

### AddAltTemplate
Appends the alternative template to the url as a querystring or folder instead of a querystring. Is "use directory urls" aware if set.
_Returns_: Complete url with alt template merged in.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| url | `System.String` | |
| altTemplateAlias | `System.String` | |
| useQueryString | `System.Boolean` | _(optional - defaults to `false`)_ |
| useDirectoryUrls | `System.Boolean` | _(optional - defaults to `GlobalSettings.UseDirectoryUrls`)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:AddAltTemplate(umbraco.library:NiceUrl($currentPage/@id), 'rss', false())" />

*****

### AppendOrUpdateQueryString
Appends or updates a query string value to supplied Url
_Returns_: The updated Url

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| url | `System.String` | _(optional - defaults to `Request.RawUrl`)_ |
| key | `System.String` | |
| value | `System.String` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:AppendOrUpdateQueryString(umbraco.library:NiceUrl($currentPage/@id), 'page', '2')" />

*****

### FormatUrl
Formats the URL - replacing characters in the string to make a 'safe' URL.
_Returns_: Returns a 'safe' URL, removing illegal characters.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| input | `System.String` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:FormatUrl($currentPage/@nodeName)" />

*****

### NiceUrl
Returns a nicely formatted Url for a given node and alternative template.
_Returns_: The NiceUrl for the node id.

This method triggers the [OnBeforeNiceUrlGenerated](#onbeforeniceurlgenerated) and[OnAfterNiceUrlGenerated](#onafterniceurlgenerated) events.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeId | `System.Int32` | |
| altTemplateAlias | `System.String` | _(optional - defaults to `null`)_ |
| useQueryString | `System.Boolean` | _(optional - defaults to `false`)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:NiceUrl($currentPage/@id, 'rss', false())" />

*****

### GetHostName
Gets the hostname of the node Id.
_Returns_: Returns the hostname for the node Id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeId | `System.Int32` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:GetHostName($currentPage/@id)" />

*****

### GetNodeIdByUrl
**Obsolete:** Please use [`ucomponents.nodes:GetNodeIdByUrl`](http://ucomponents.org/xslt-extensions/nodes/#getnodeidbyurl).

*****

### GetTextByUrl
Gets the text by URL.
_Returns_: Returns the text (System.String) from a given URL.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| url | `System.String` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:GetTextByUrl('http://ucomponents.org/LICENSE')" />

*****

### GetXmlNodeByUrl
**Obsolete:** Please use [`ucomponents.nodes:GetXmlNodeByUrl`](http://ucomponents.org/xslt-extensions/nodes/#getxmlnodebyurl).

*****

### GuessNiceUrl
Guesses the NiceUrl based on the node id.
_Returns_: Returns a guestimate of the NiceUrl for a node id.

`GuessNiceUrl` is not very performant when attempting to guess the URL for unpublished nodes.
Do not over-use this method. It makes many database calls and will be slow!

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeId | `System.Int32` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.urls:GuessNiceUrl(1066)" />


*****

### OnBeforeNiceUrlGenerated
Dispatches a BeforeNiceUrlGenerated event.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeId | `System.Int32` | |

#### C# Example

	uComponents.XsltExtensions.Urls.BeforeNiceUrlGenerated += Urls_BeforeNiceUrlGenerated;

*****

### OnAfterNiceUrlGenerated
Dispatches an AfterNiceUrlGenerated event.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeId | `System.Int32` | |
| url | `System.String` | |

#### C# Example

	uComponents.XsltExtensions.Urls.AfterNiceUrlGenerated += Urls_AfterNiceUrlGenerated;

*****

