---
layout: extension
title: Email
category: XSLT Extensions
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Email" alias="ucomponents.email" />
		...
	</XsltExtensions>

## Methods
Here are available methods:

### IsValidEmail
Determines whether [is valid email] [the specified input].
_Returns_: true if [is valid email] [the specified input]; otherwise, false.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.email:IsValidEmail(input)" />


*****

### SendMail
Sends an email. Performs the same function an umbraco.library.SendMail, with the option of sending via SSL.

#### Parameters
| Name | Type |
|------|------|
| from | System.String |
| to | System.String |
| subject | System.String |
| body | System.String |
| isHtml | System.Boolean |
| useSSL | System.Boolean |

#### XSLT Example

	<xsl:value-of select="ucomponents.email:SendMail(from, to, subject, body, isHtml, useSSL)" />


*****

