---
layout: extension
title: Strings
category: XSLT Extensions
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Strings" alias="ucomponents.strings" />
		...
	</XsltExtensions>

## Methods
Here are available methods:

### GetFirstWords
Return the first amount of words defined by 'count' contained in 'text'.
_Returns_: String containing only the first x words.

#### Parameters
| Name | Type |
|------|------|
| text | System.String |
| count | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:GetFirstWords(text, count)" />


*****

### GetFirstWords
Return the first amount of words defined by 'count' contained in 'text'.
_Returns_: String containing only the first x words.

#### Parameters
| Name | Type |
|------|------|
| text | System.String |
| count | System.Int32 |
| appender | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:GetFirstWords(text, count, appender)" />


*****

### MakeEmailHyperlink
Converts an email address into a hyperlink.

#### Parameters
| Name | Type |
|------|------|
| email | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:MakeEmailHyperlink(email)" />


*****

### MakeEmailHyperlink
Converts an email address into a hyperlink.

#### Parameters
| Name | Type |
|------|------|
| email | System.String |
| text | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:MakeEmailHyperlink(email, text)" />


*****

### MakeUrlHyperlink
Converts all URLs into hyperlinks within a string.
_Returns_: Returns a string with all URLs turned into hyperlinks.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:MakeUrlHyperlink(input)" />


*****

### PathShortener
Truncates the middle section of a string, this is ideal for long filepaths or URLs.
_Returns_: Returns a shortened path of the string.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:PathShortener(input)" />


*****

### TruncateInner
Truncates the inner-string.
_Returns_: Returns a string with the mid-section truncated.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |
| maxLength | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:TruncateInner(input, maxLength)" />


*****

### RemoveChars
Removes non alpha-numeric characters from a string.
_Returns_: Returns the string with non alpha-numeric characters removed.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:RemoveChars(input)" />


*****

### Reverse
Reverses the specified input.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Reverse(input)" />


*****

### SafeAlias
Makes an alias name safe to use as an XML element name.
            Removes all spaces and non-alphanumeric characters.
_Returns_: Returns a safe alias string.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:SafeAlias(input)" />


*****

### SpaceOutCamelCase
Spaces out a string on capitals or numbers.
_Returns_: The string with spaces before each capital letter or number

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:SpaceOutCamelCase(input)" />


*****

### StripFontTags
Strips the <font> tags from a string.
_Returns_: Returns the string stripped of all <font> tags.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:StripFontTags(input)" />


*****

### StripHTML
Strips the HTML.
_Returns_: Returns the string stripped of all HTML tags.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:StripHTML(input)" />


*****

### StripWhitespace
Strips the whitespace characters from a string.
_Returns_: Returns the string stripped of any whitespace characters.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:StripWhitespace(input)" />


*****

### StripNonAlphaNumeric
Strips the non alpha-numeric characters.
_Returns_: Returns the string with only alpha-numeric characters.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:StripNonAlphaNumeric(input)" />


*****

### StripLineBreaks
Strips out all the line-breaks.
_Returns_: Returns the string with all the line-breaks stripped out.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:StripLineBreaks(input)" />


*****

### ToLowerCase
Changes the case of the string to lowercase.
_Returns_: Returns the string as lowercase.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ToLowerCase(input)" />


*****

### ToUpperCase
Changes the case of the string to uppercase.
_Returns_: Returns the string as uppercase.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ToUpperCase(input)" />


*****

### ConvertToCamelCase
Changes a string to camelCase
_Returns_: The camelCased string

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ConvertToCamelCase(input)" />


*****

### ToCamelCase
Changes a string to camelCase
_Returns_: The camelCased string

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ToCamelCase(input)" />


*****

### ToProperCase
Changes the case of the string to proper case.
_Returns_: Returns the string in proper case.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ToProperCase(input)" />


*****

### ToTitleCase
Changes the case of the string to title case.
_Returns_: Returns the string in title case.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ToTitleCase(input)" />


*****

### ToBase64String
Encodes a string as Base64.
_Returns_: Returns the string encoded as Base64.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ToBase64String(input)" />


*****

### FromBase64String
Decodes a string from Base64.
_Returns_: Returns the decoded Base64 string.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:FromBase64String(input)" />


*****

### WordCount
Counts the number of words in a string.
_Returns_: Returns the number of words in the string.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:WordCount(input)" />


*****

### LowerCaseTags
Lowers the case of the HTML tags.
_Returns_: Returns the string with all HTML tags in lowercase.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:LowerCaseTags(input)" />


*****

### Coalesce
Performs a Coalesce among the supplied arguments.
_Returns_: Returns the first nonnull or empty expression among the supplied arguments.

#### Parameters
| Name | Type |
|------|------|
| arg1 | System.String |
| arg2 | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Coalesce(arg1, arg2)" />


*****

### Coalesce
Performs a Coalesce among the supplied arguments.
_Returns_: Returns the first nonnull or empty expression among the supplied arguments.

#### Parameters
| Name | Type |
|------|------|
| arg1 | System.String |
| arg2 | System.String |
| arg3 | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Coalesce(arg1, arg2, arg3)" />


*****

### Coalesce
Performs a Coalesce among the supplied arguments.
_Returns_: Returns the first nonnull or empty expression among the supplied arguments.

#### Parameters
| Name | Type |
|------|------|
| arg1 | System.String |
| arg2 | System.String |
| arg3 | System.String |
| arg4 | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Coalesce(arg1, arg2, arg3, arg4)" />


*****

### Coalesce
Performs a Coalesce among the supplied arguments.
_Returns_: Returns the first nonnull or empty expression among the supplied arguments.

#### Parameters
| Name | Type |
|------|------|
| arg1 | System.String |
| arg2 | System.String |
| arg3 | System.String |
| arg4 | System.String |
| arg5 | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Coalesce(arg1, arg2, arg3, arg4, arg5)" />


*****

### Format
Formats the specified string.
_Returns_: Returns a formatted string.

#### Parameters
| Name | Type |
|------|------|
| format | System.String |
| arg1 | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Format(format, arg1)" />


*****

### Format
Formats the specified string.
_Returns_: Returns a formatted string.

#### Parameters
| Name | Type |
|------|------|
| format | System.String |
| arg1 | System.String |
| arg2 | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Format(format, arg1, arg2)" />


*****

### Format
Formats the specified string.
_Returns_: Returns a formatted string.

#### Parameters
| Name | Type |
|------|------|
| format | System.String |
| arg1 | System.String |
| arg2 | System.String |
| arg3 | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Format(format, arg1, arg2, arg3)" />


*****

### Format
Formats the specified string.
_Returns_: Returns a formatted string.

#### Parameters
| Name | Type |
|------|------|
| format | System.String |
| arg1 | System.String |
| arg2 | System.String |
| arg3 | System.String |
| arg4 | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Format(format, arg1, arg2, arg3, arg4)" />


*****

### Format
Formats the specified string.
_Returns_: Returns a formatted string.

#### Parameters
| Name | Type |
|------|------|
| format | System.String |
| arg1 | System.String |
| arg2 | System.String |
| arg3 | System.String |
| arg4 | System.String |
| arg5 | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Format(format, arg1, arg2, arg3, arg4, arg5)" />


*****

### Concat
Concats the specified nodeset.

#### Parameters
| Name | Type |
|------|------|
| nodeset | System.Xml.XPath.XPathNodeIterator |
| separator | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Concat(nodeset, separator)" />


*****

### RemoveDuplicateEntries
Removes the duplicate entries from a comma-separated list.
_Returns_: Returns a comma-separated list with duplicate entries removed.

#### Parameters
| Name | Type |
|------|------|
| list | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:RemoveDuplicateEntries(list)" />


*****

### RemoveDuplicateEntries
Removes the duplicate entries from a comma-separated list.
_Returns_: Returns a comma-separated list with duplicate entries removed.

#### Parameters
| Name | Type |
|------|------|
| list | System.String |
| separator | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:RemoveDuplicateEntries(list, separator)" />


*****

### RemoveDuplicateEntries
Removes the duplicate entries from a delimited list.
_Returns_: Returns a delimited list with duplicate entries removed.

#### Parameters
| Name | Type |
|------|------|
| list | System.String |
| separators | System.Char[] |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:RemoveDuplicateEntries(list, separators)" />


*****

### RemoveEmptyEntries
Removes the empty entries from a comma-separated list.
_Returns_: Returns a comma-separated list with empty entries removed.

#### Parameters
| Name | Type |
|------|------|
| list | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:RemoveEmptyEntries(list)" />


*****

### RemoveEmptyEntries
Removes the empty entries from a comma-separated list.
_Returns_: Returns a comma-separated list with empty entries removed.

#### Parameters
| Name | Type |
|------|------|
| list | System.String |
| separator | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:RemoveEmptyEntries(list, separator)" />


*****

### RemoveEmptyEntries
Removes the empty entries from a delimited list.
_Returns_: Returns a the delimited list with the empty entries removed.

#### Parameters
| Name | Type |
|------|------|
| list | System.String |
| separators | System.Char[] |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:RemoveEmptyEntries(list, separators)" />


*****

### SingularPlural
Selects a singular or plural word based on the value of the count.
_Returns_: Returns the singular or plural word based on the count's value.

#### Parameters
| Name | Type |
|------|------|
| count | System.Int32 |
| singular | System.String |
| plural | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:SingularPlural(count, singular, plural)" />


*****

### SingularPlural
Selects a singular or plural word based on the value of the count.

#### Parameters
| Name | Type |
|------|------|
| count | System.Int32 |
| singular | System.String |
| plural | System.String |
| prefixCount | System.Boolean |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:SingularPlural(count, singular, plural, prefixCount)" />


*****

### TrimStringFromStart
Removes the specified string from the beginning of the target, if it exists.
_Returns_: Returns the input string with the specified text trimmed from the start.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |
| textToTrim | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:TrimStringFromStart(input, textToTrim)" />


*****

### TrimStringFromEnd
Removes the specified string from the end of the target, if it exists.
_Returns_: Returns the input string with the specified text trimmed from the end.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |
| textToTrim | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:TrimStringFromEnd(input, textToTrim)" />


*****

### CharLoop
Loops through each of the characters in the string.
_Returns_: Returns a string that has been passed through the character condition filtered.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |
| condition | CharCondition |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:CharLoop(input, condition)" />


*****

### Coalesce
Performs a Coalesce among the supplied arguments.
_Returns_: Returns the first nonnull or empty expression among the supplied arguments.

#### Parameters
| Name | Type |
|------|------|
| args | System.String[] |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Coalesce(args)" />


*****

### FormatString
Formats the specified string.
_Returns_: Returns a formatted string.

#### Parameters
| Name | Type |
|------|------|
| format | System.String |
| args | System.String[] |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:FormatString(format, args)" />


*****

