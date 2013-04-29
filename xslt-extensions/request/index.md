---
layout: extension
title: Request
category: XSLT Extensions
since_version: 3.0
---

## Activation

### Version 6.0.0 (and above)
As of uComponents v6.0.0 all XSLT extensions are automatically registered with Umbraco. Newly created XSLT files (in the back-office) will already contain the appropriate namespaces.  For existing XSLT files, you will still need to add the `ucomponents.request` namespace.

### Prior to version 6.0.0

Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Request" alias="ucomponents.request" />
		...
	</XsltExtensions>

*****

## Methods
Here are available methods in the `Request` library:

* [Cookies](#cookies)
* [Form](#form)
* [QueryString](#querystring)
* [ServerVariables](#servervariables)

*****

### Cookies
Converts the `Request.Cookies` object into a node-set.<br/>
_Returns_: Returns a `XPathNodeIterator` object that represents the `Request.Cookies` object.


#### XSLT Example

	<table>
		<thead>
			<tr>
				<th>Name</th>
				<th>Expires</th>
				<th>Path</th>
				<th>Value</th>
			</tr>
		</thead>
		<tbody>
			<xsl:for-each select="ucomponents.request:Cookies()/Request.Cookies/cookie">
				<tr>
					<td>
						<xsl:value-of select="@name" />
					</td>
					<td>
						<xsl:value-of select="@expires" />
					</td>
					<td>
						<xsl:value-of select="@path" />
					</td>
					<td>
						<xsl:value-of select="value" />
					</td>
				</tr>
			</xsl:for-each>
		</tbody>
	</table>

*****

### Form
Converts the `Request.Form` object into a node-set.<br/>
_Returns_: Returns a `XPathNodeIterator` object that represents the `Request.Form` object.


#### XSLT Example

	<dl>
		<xsl:for-each select="ucomponents.request:Form()/Request.Form/*">
			<dt>
				<xsl:value-of select="name()" />
			</dt>
			<dd>
				<xsl:value-of select="text()" />
			</dd>
		</xsl:for-each>
	</dl>

*****

### QueryString
Converts the Request.QueryString object into a node-set.<br/>
_Returns_: Returns a `XPathNodeIterator` object that represents the `Request.QueryString` object.


#### XSLT Example

	<dl>
		<xsl:for-each select="ucomponents.request:QueryString()/Request.QueryString/*">
			<dt>
				<xsl:value-of select="name()" />
			</dt>
			<dd>
				<xsl:value-of select="text()" />
			</dd>
		</xsl:for-each>
	</dl>

*****

### ServerVariables
Converts the `Request.ServerVariables` object into a node-set.<br/>
_Returns_: Returns a `XPathNodeIterator` object that represents the `Request.ServerVariables` object.


#### XSLT Example

	<dl>
		<xsl:for-each select="ucomponents.request:ServerVariables()/Request.ServerVariables/*">
			<dt>
				<xsl:value-of select="name()" />
			</dt>
			<dd>
				<xsl:value-of select="text()" />
			</dd>
		</xsl:for-each>
	</dl>

*****
