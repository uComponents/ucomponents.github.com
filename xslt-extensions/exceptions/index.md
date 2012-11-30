---
layout: extension
title: Exceptions
category: XSLT Extensions
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Exceptions" alias="ucomponents.exceptions" />
		...
	</XsltExtensions>

## Methods
Here are available methods:

### ToXml
Returns the Exception message as XML.
_Returns_: An XDocument of the Exception object.

#### Parameters
| Name | Type |
|------|------|
| exception | System.Exception |

#### XSLT Example

	<xsl:value-of select="ucomponents.exceptions:ToXml(exception)" />


*****

### ToXPathNodeIterator
Returns the Exception message as a XPathNodeIterator object.
_Returns_: An XPathNodeIterator instance of the Exception object.

#### Parameters
| Name | Type |
|------|------|
| exception | System.Exception |

#### XSLT Example

	<xsl:value-of select="ucomponents.exceptions:ToXPathNodeIterator(exception)" />


*****

