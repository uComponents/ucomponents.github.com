---
layout: extension
title: Media
category: XSLT Extensions
since_version: 2.1
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Media" alias="ucomponents.media" />
		...
	</XsltExtensions>

*****

## Methods
Here are available methods in the ```Media``` library:

* [GetMediaByCsv](#getmediabycsv)
* [GetMediaByCsv](#getmediabycsv)
* [GetMediaByName](#getmediabyname)
* [GetMediaByType](#getmediabytype)
* [GetMediaByUrlName](#getmediabyurlname)
* [GetMediaByXPath](#getmediabyxpath)
* [GetMediaIdByUrl](#getmediaidbyurl)
* [GetPublishedXml](#getpublishedxml)
* [GetUniqueId](#getuniqueid)
* [GetImageHtml](#getimagehtml)
* [GetImageHtml](#getimagehtml)
* [GetImageHeight](#getimageheight)
* [GetImageWidth](#getimagewidth)
* [GetImageHeightAndWidth](#getimageheightandwidth)
* [GetImageSize](#getimagesize)

*****

### GetMediaByCsv
Gets the media by CSV.
_Returns_: Returns an XPathNodeIterator of the media nodes from the CSV list.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| csv | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetMediaByCsv(csv)" />


*****

### GetMediaByCsv
Gets the media by CSV.
_Returns_: Returns an XPathNodeIterator of the media nodes from the CSV list.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| csv | ```System.String``` | |
| deep | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetMediaByCsv(csv, deep)" />


*****

### GetMediaByName
Gets the media item by it's node name.
_Returns_: Returns an XPathNodeIterator of the media nodes from specified node name.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeName | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetMediaByName(nodeName)" />


*****

### GetMediaByType
Gets the media items by node type alias.
_Returns_: Returns an XPathNodeIterator of the media nodes from specified node type alias.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeTypeAlias | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetMediaByType(nodeTypeAlias)" />


*****

### GetMediaByUrlName
Gets the media items by URL name.
_Returns_: Returns an XPathNodeIterator of the media nodes from specified URL name.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| urlName | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetMediaByUrlName(urlName)" />


*****

### GetMediaByXPath
Gets the media items by an XPath expression.
_Returns_: Returns an XPathNodeIterator of the media nodes from specified XPath expression.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| xpath | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetMediaByXPath(xpath)" />


*****

### GetMediaIdByUrl
Gets the media Id by URL.
_Returns_: Returns the media Id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| url | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetMediaIdByUrl(url)" />


*****

### GetPublishedXml
Gets the published Xml.
_Returns_: Returns an XPathNodeIterator of all the media nodes.


#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetPublishedXml()" />


*****

### GetUniqueId
Gets the unique id of a media node.
_Returns_: Returns the unique id of a media node.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| mediaId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetUniqueId(mediaId)" />


*****

### GetImageHtml
Gets the HTML for an image tag, using the Media Id.
_Returns_: Returns a HTML image tag from a Media Id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| mediaId | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetImageHtml(mediaId)" />


*****

### GetImageHtml
Gets the HTML for an image tag, using the Media Id.
_Returns_: Returns a HTML image tag from a Media Id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| mediaId | ```System.String``` | |
| defaultHeight | ```System.Int32``` | |
| defaultWidth | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetImageHtml(mediaId, defaultHeight, defaultWidth)" />


*****

### GetImageHeight
Gets the height of the image.
_Returns_: Returns the height of the image.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetImageHeight(path)" />


*****

### GetImageWidth
Gets the width of the image.
_Returns_: Returns the width of the image.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetImageWidth(path)" />


*****

### GetImageHeightAndWidth
Gets the height and width of the image.
_Returns_: Returns the height and width of the image.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |
| height | ```System.Int32@``` | |
| width | ```System.Int32@``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetImageHeightAndWidth(path, height, width)" />


*****

### GetImageSize
Gets the size of the image.
_Returns_: Returns the size (dimensions) of the image.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.media:GetImageSize(path)" />


*****

