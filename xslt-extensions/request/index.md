---
layout: extension
title: Request
category: XSLT Extensions
since_version: 3.0
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Request" alias="ucomponents.request" />
		...
	</XsltExtensions>

## Methods
Here are available methods:

### ServerVariables
Converts the Request.ServerVariables object into a XPathNodeIterator object.
_Returns_: Returns a XPathNodeIterator object that represents the Request.ServerVariables object.


#### XSLT Example

	<xsl:value-of select="ucomponents.request:ServerVariables()" />


*****

### QueryString
Converts the Request.QueryString object into a XPathNodeIterator object.
_Returns_: Returns a XPathNodeIterator object that represents the Request.QueryString object.


#### XSLT Example

	<xsl:value-of select="ucomponents.request:QueryString()" />


*****

### Form
Converts the Request.Form object into a XPathNodeIterator object.
_Returns_: Returns a XPathNodeIterator object that represents the Request.Form object.


#### XSLT Example

	<xsl:value-of select="ucomponents.request:Form()" />


*****

### Cookies
Converts the Request.Cookies object into a XPathNodeIterator object.
_Returns_: Returns a XPathNodeIterator object that represents the Request.Cookies object.


#### XSLT Example

	<xsl:value-of select="ucomponents.request:Cookies()" />


*****

### ConvertNameValueCollectionToXPathNodeIterator
Iterates over the NameValueCollection, appending each entry to an XmlTextNode.
_Returns_: Returns a XPathNodeIterator object that represents the NameValueCollection.

#### Parameters
| Name | Type |
|------|------|
| rootName | System.String |
| nvc | System.Collections.Specialized.NameValueCollection |

#### XSLT Example

	<xsl:value-of select="ucomponents.request:ConvertNameValueCollectionToXPathNodeIterator(rootName, nvc)" />


*****

