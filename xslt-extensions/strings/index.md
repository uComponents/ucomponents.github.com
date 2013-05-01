---
layout: extension
title: Strings
category: XSLT Extensions
since_version: 1.0.0
---

## Activation

### Version 6.0.0 (and above)
As of uComponents v6.0.0 all XSLT extensions are automatically registered with Umbraco. Newly created XSLT files (in the back-office) will already contain the appropriate namespaces.  For existing XSLT files, you will still need to add the `ucomponents.strings` namespace.

### Prior to version 6.0.0

Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Strings" alias="ucomponents.strings" />
		...
	</XsltExtensions>

*****

## Methods
Here are available methods in the `Strings` library:

* [Coalesce](#coalesce)
* [Concat](#concat)
* [Format](#format)
* [FromBase64String](#frombase64string)
* [GetFirstWords](#getfirstwords)
* [LowerCaseTags](#lowercasetags)
* [MakeEmailHyperlink](#makeemailhyperlink)
* [MakeUrlHyperlink](#makeurlhyperlink)
* [PathShortener](#pathshortener)
* [RemoveChars](#removechars)
* [RemoveDuplicateEntries](#removeduplicateentries)
* [RemoveEmptyEntries](#removeemptyentries)
* [Reverse](#reverse)
* [SafeAlias](#safealias)
* [SingularPlural](#singularplural)
* [SpaceOutCamelCase](#spaceoutcamelcase)
* [StripFontTags](#stripfonttags)
* [StripHTML](#striphtml)
* [StripLineBreaks](#striplinebreaks)
* [StripNonAlphaNumeric](#stripnonalphanumeric)
* [StripWhitespace](#stripwhitespace)
* [ToBase64String](#tobase64string)
* [ToCamelCase](#tocamelcase)
* [ToLowerCase](#tolowercase)
* [ToProperCase](#topropercase)
* [ToTitleCase](#totitlecase)
* [ToUpperCase](#touppercase)
* [TrimStringFromStart](#trimstringfromstart)
* [TrimStringFromEnd](#trimstringfromend)
* [TruncateInner](#truncateinner)
* [WordCount](#wordcount)

*****

### GetFirstWords
Return the first amount of words defined by 'count' contained in 'text'.<br>
_Returns_: String containing only the first x words.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| text | `System.String` | |
| count | `System.Int32` | |
| appender | `System.String` | _(optional - defaults to `&#8230;`)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:GetFirstWords($currentPage/bodyText, 30, '...')" disable-output-escaping="yes" />

*****

### MakeEmailHyperlink
Converts an email address into a hyperlink.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| email | `System.String` | |
| text | `System.String` | _(optional - defaults to `email`)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:MakeEmailHyperlink('username@domain.com', 'Click here to email me.')" disable-output-escaping="yes" />

*****

### MakeUrlHyperlink
Converts all URLs into hyperlinks within a string.<br>
_Returns_: Returns a string with all URLs turned into hyperlinks.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:MakeUrlHyperlink(umbraco.library:NiceUrl($currentPage/@id))" disable-output-escaping="yes" />

*****

### PathShortener
Truncates the middle section of a string, this is ideal for long filepaths or URLs.<br>
_Returns_: Returns a shortened path of the string.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:PathShortener(umbraco.library:NiceUrl($currentPage/@id))" />

*****

### TruncateInner
Truncates the inner-string.<br>
_Returns_: Returns a string with the mid-section truncated.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |
| maxLength | `System.Int32` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:TruncateInner($currentPage/@nodeName, 30)" />

*****

### RemoveChars
Removes non alpha-numeric characters from a string.<br>
_Returns_: Returns the string with non alpha-numeric characters removed.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:RemoveChars($currentPage/@nodeName)" />

*****

### Reverse
Reverses the specified input.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Reverse($currentPage/@nodeName)" />

*****

### SafeAlias
Makes an alias name safe to use as an XML element name. Removes all spaces and non-alphanumeric characters.<br>
_Returns_: Returns a safe alias string.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:SafeAlias($currentPage/@nodeName)" />

*****

### SpaceOutCamelCase
Spaces out a string on capitals or numbers.<br>
_Returns_: The string with spaces before each capital letter or number

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:SpaceOutCamelCase(name($currentPage))" />

*****

### StripFontTags
Strips the `<font>` tags from a string.<br>
_Returns_: Returns the string stripped of all `<font>` tags.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:StripFontTags($currentPage/bodyText)" disable-output-escaping="yes" />

*****

### StripHTML
Strips the HTML.<br>
_Returns_: Returns the string stripped of all HTML tags.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:StripHTML($currentPage/bodyText)" />

*****

### StripWhitespace
Strips the whitespace characters from a string.<br>
_Returns_: Returns the string stripped of any whitespace characters.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:StripWhitespace($currentPage/introText)" />

*****

### StripNonAlphaNumeric
Strips the non alpha-numeric characters.<br>
_Returns_: Returns the string with only alpha-numeric characters.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:StripNonAlphaNumeric($currentPage/@nodeName)" />

*****

### StripLineBreaks
Strips out all the line-breaks.<br>
_Returns_: Returns the string with all the line-breaks stripped out.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:StripLineBreaks($currentPage/introText)" />

*****

### ToLowerCase
Changes the case of the string to lowercase.<br>
_Returns_: Returns the string as lowercase.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ToLowerCase($currentPage/@nodeName)" />

*****

### ToUpperCase
Changes the case of the string to uppercase.<br>
_Returns_: Returns the string as uppercase.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ToUpperCase($currentPage/@nodeName)" />

*****

### ToCamelCase
Changes a string to camelCase.<br>
_Returns_: The camelCased string

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ToCamelCase($currentPage/@nodeName)" />


*****

### ToProperCase
Changes the case of the string to proper case.<br>
_Returns_: Returns the string in proper case.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ToProperCase($currentPage/@nodeName)" />

*****

### ToTitleCase
Changes the case of the string to title case.<br>
_Returns_: Returns the string in title case.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ToTitleCase($currentPage/@nodeName)" />

*****

### ToBase64String
Encodes a string as Base64.<br>
_Returns_: Returns the string encoded as Base64.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:ToBase64String('A string to be converted to Base64.')" />

*****

### FromBase64String
Decodes a string from Base64.<br>
_Returns_: Returns the decoded Base64 string.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:FromBase64String('QSBCYXNlNjQgZW5jb2RlZCBzdHJpbmcu')" />

*****

### WordCount
Counts the number of words in a string.<br>
_Returns_: Returns the number of words in the string.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:WordCount($currentPage/introText)" />

*****

### LowerCaseTags
Lowers the case of the HTML tags.<br>
_Returns_: Returns the string with all HTML tags in lowercase.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:LowerCaseTags($currentPage/bodyText)" disable-output-escaping="yes" />

*****

### Coalesce
Performs a Coalesce among the supplied arguments.
_Returns_: Returns the first non-null or empty expression among the supplied arguments.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| arg1 | `System.String` | |
| arg2 | `System.String` | |
| arg3 | `System.String` | _(optional)_ |
| arg4 | `System.String` | _(optional)_ |
| arg5 | `System.String` | _(optional)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Coalesce(customTitle, introTitle, pageSubtitle, pageTitle, @nodeName)" />

*****

### Format
Formats the specified string.
_Returns_: Returns a formatted string.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| format | `System.String` | _A composite format string ([uses .NET syntax](http://msdn.microsoft.com/en-gb/library/txafckwd.aspx))._ |
| arg1 | `System.String` | |
| arg2 | `System.String` | _(optional)_ |
| arg3 | `System.String` | _(optional)_ |
| arg4 | `System.String` | _(optional)_ |
| arg5 | `System.String` | _(optional)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Format('{0} {1} {2} {3:ddMMyy} {4:ddMMyy}', @id, @nodeName, @urlName, @createDate, @updateDate)" />

*****

### Concat
Concats the specified nodeset.

#### Parameters
| Name | Type |
|------|------|
| nodeset | System.Xml.XPath.XPathNodeIterator |
| separator | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:Concat($currentPage/widgets/*/nodeId, ',')" />

*****

### RemoveDuplicateEntries
Removes the duplicate entries from a comma-separated list.<br>
_Returns_: Returns a comma-separated list with duplicate entries removed.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| list | `System.String` | |
| separator | `System.String` | _(optional - defaults to a comma `,`)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:RemoveDuplicateEntries('aaa,bbb,ccc,ddd,aaa,ccc,eee', ',')" />

*****

### RemoveEmptyEntries
Removes the empty entries from a comma-separated list.<br>
_Returns_: Returns a comma-separated list with empty entries removed.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| list | `System.String` | |
| separator | `System.String` | _(optional - defaults to a comma `,`)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:RemoveEmptyEntries('aaa,bbb,ccc,,ddd,,,,,eee', ',')" />

*****

### SingularPlural
Selects a singular or plural word based on the value of the count.<br>
_Returns_: Returns the singular or plural word based on the count's value.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| count | `System.Int32` | |
| singular | `System.String` | |
| plural | `System.String` | |
| prefixCount | System.Boolean | _(optional - defaults to `false`)_ |

#### XSLT Example

	<xsl:text>You have selected </xsl:text>
	<xsl:value-of select="ucomponents.strings:SingularPlural(count($currentPage/widgets/*/nodeId), 'node.', 'nodes.', true())" />

*****

### TrimStringFromStart
Removes the specified string from the beginning of the target, if it exists.<br>
_Returns_: Returns the input string with the specified text trimmed from the start.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |
| textToTrim | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:TrimStringFromStart($currentPage/@nodeName, 'Some prefix: ')" />

*****

### TrimStringFromEnd
Removes the specified string from the end of the target, if it exists.<br>
_Returns_: Returns the input string with the specified text trimmed from the end.

#### Parameters
| Name | Type |
|------|------|
| input | `System.String` |
| textToTrim | `System.String` |

#### XSLT Example

	<xsl:value-of select="ucomponents.strings:TrimStringFromEnd($currentPage/@nodeName, '! Some suffix')" />

*****
