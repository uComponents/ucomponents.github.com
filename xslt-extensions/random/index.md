---
layout: extension
title: Random
category: XSLT Extensions
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Random" alias="ucomponents.random" />
		...
	</XsltExtensions>

## Methods
Here are available methods:

### GetRandomDouble
Gets the random double.
_Returns_: Returns a random dobule.


#### XSLT Example

	<xsl:value-of select="ucomponents.random:GetRandomDouble()" />


*****

### GetRandomItemsFromCsv
Gets the random items from CSV.
_Returns_: Returns a random selection of items from the original comma-separated values.

#### Parameters
| Name | Type |
|------|------|
| csv | System.String |
| count | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.random:GetRandomItemsFromCsv(csv, count)" />


*****

### GetRandomGuid
Gets the random GUID.
_Returns_: Returns a random GUID.


#### XSLT Example

	<xsl:value-of select="ucomponents.random:GetRandomGuid()" />


*****

### GetRandomGuid
Gets the random GUID, with a specified format.
_Returns_: Returns a random GUID, with a specified format.

#### Parameters
| Name | Type |
|------|------|
| format | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.random:GetRandomGuid(format)" />


*****

### GetRandomNumber
Gets the random number.
_Returns_: Returns a random integer.


#### XSLT Example

	<xsl:value-of select="ucomponents.random:GetRandomNumber()" />


*****

### GetRandomNumber
Gets the random number.
_Returns_: Returns a random integer, less than specified maximum.

#### Parameters
| Name | Type |
|------|------|
| maximum | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.random:GetRandomNumber(maximum)" />


*****

### GetRandomNumber
Gets the random number.
_Returns_: Returns a random integer, between the specified minimum and maximum.

#### Parameters
| Name | Type |
|------|------|
| minimum | System.Int32 |
| maximum | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.random:GetRandomNumber(minimum, maximum)" />


*****

### GetRandomNumbers
Gets the random numbers.
_Returns_: Returns a sequence of random numbers.

#### Parameters
| Name | Type |
|------|------|
| count | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.random:GetRandomNumbers(count)" />


*****

### GetRandomNumbersAsXml
Gets the random numbers as XML.
_Returns_: Returns a sequence of random numbers as an XML node-set.

#### Parameters
| Name | Type |
|------|------|
| count | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.random:GetRandomNumbersAsXml(count)" />


*****

### GetRandomString
Gets the random string.
_Returns_: Returns a sequence of random characters in a string.

#### Parameters
| Name | Type |
|------|------|
| count | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.random:GetRandomString(count)" />


*****

### GenerateRandomString
Generates the random string.
_Returns_: Returns the specified pattern with characters replaced with random characters.

#### Parameters
| Name | Type |
|------|------|
| pattern | System.String |
| replacer | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.random:GenerateRandomString(pattern, replacer)" />


*****

