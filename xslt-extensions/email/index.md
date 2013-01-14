---
layout: extension
title: Email
category: XSLT Extensions
since_version: 3.0
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Email" alias="ucomponents.email" />
		...
	</XsltExtensions>

*****

## Methods
Here are available methods in the ```Email``` library:

* [IsValidEmail](#isvalidemail)
* [SendMail](#sendmail)

*****

### IsValidEmail
Determines whether the input is a valid email address.<br>
_Returns_: true if valid; otherwise, false.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| input | ```System.String``` | The email address. |

#### XSLT Example

	<!-- Testing an email address; where 'emailAddress' is a node -->
	<xsl:choose>
		<xsl:when test="ucomponents.email:IsValidEmail(emailAddress)">
			<p>This is a valid email address.</p>
		</xsl:when>
		<xsl:otherwise>
			<p>This is not a valid email address.</p>
		</xsl:otherwise>
	</xsl:choose>

*****

### SendMail
Sends an email. Performs the exact same function an ```umbraco.library.SendMail```, with the option of sending via SSL.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| from | ```System.String``` | |
| to | ```System.String``` | |
| subject | ```System.String``` | |
| body | ```System.String``` | |
| isHtml | ```System.Boolean``` | |
| useSSL | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.email:SendMail('no-reply@localhost', 'test@localhost', 'Test message', 'This is a test message.', false(), true())" />

*****

