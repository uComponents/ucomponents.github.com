---
layout: extension
title: Cms
category: XSLT Extensions
since_version: 1.0.0
---

## Activation

### Version 6.0.0 (and above)
As of uComponents v6.0.0 all XSLT extensions are automatically registered with Umbraco. Newly created XSLT files (in the back-office) will already contain the appropriate namespaces.  For existing XSLT files, you will still need to add the `ucomponents.cms` namespace.

### Prior to version 6.0.0

Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Cms" alias="ucomponents.cms" />
		...
	</XsltExtensions>

*****

## Methods
Here are available methods in the `Cms` library:

#### Data Types
* [GetDataTypes](#getdatatypes)
* [GetDataTypeByGuid](#getdatatypebyguid)
* [GetDataTypeById](#getdatatypebyid)

#### Document Types
* [GetDocumentTypes](#getdocumenttypes)
* [GetDocumentType](#getdocumenttype)

#### Languages
* [GetLanguages](#getlanguages)
* [GetLanguage](#getlanguage)
* [GetLanguageByCultureCode](#getlanguagebyculturecode)
* [GetLanguageByNodeId](#getlanguagebynodeid)
* [GetLanguageIdByNodeId](#getlanguageidbynodeid)

#### Macros
* [GetMacros](#getmacros)
* [GetMacro](#getmacro)

#### Media Types
* [GetMediaTypes](#getmediatypes)
* [GetMediaType](#getmediatype)

#### Member Types
* [GetMemberTypes](#getmembertypes)
* [GetMemberType](#getmembertype)

#### Templates
* [GetTemplates](#gettemplates)
* [GetTemplateAlias](#gettemplatealias)
* [GetTemplateById](#gettemplatebyid)
* [GetTemplateByAlias](#gettemplatebyalias)
* [GetTemplateIdByAlias](#gettemplateidbyalias)

#### Users
* [GetAllUsers](#getallusers)
* [GetAllUsersByEmail](#getallusersbyemail)
* [GetAllUsersByLoginName](#getallusersbyloginname)
* [GetUser](#getuser)
* [GetUserEmail](#getuseremail)
* [GetUserLanguage](#getuserlanguage)
* [GetUserLoginName](#getuserloginname)
* [GetUserName](#getusername)
* [GetUserTypeAlias](#getusertypealias)

#### General
* [GetContentIdByPropertyId](#getcontentidbypropertyid)
* [GetDictionaryItem](#getdictionaryitem)
* [GetUniqueId](#getuniqueid)
* [IsLegacyXmlSchema](#islegacyxmlschema)
* [InPreviewMode](#inpreviewmode)

*****

## Data Types

### GetDataTypes
Returns an `XPathNodeIterator` of all the data types created in Umbraco.<br>
_Returns_: A node-set of all the data types used within Umbraco.

#### XSLT Example

	<ul>
		<xsl:for-each select="ucomponents.cms:GetDataTypes()/DataType">
			<li>
				<xsl:value-of select="@Name" />
			</li>
		</xsl:for-each>
	</ul>

*****

### GetDataTypeByGuid
Returns an `XPathNodeIterator` of the specified data-type by a `Guid` (`string`).<br>
_Returns_: A node-set of the specified data-type

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| dataTypeGuid | `System.String` | |

#### XSLT Example

	<xsl:variable name="dataType" select="ucomponents.cms:GetDataTypeByGuid('0CC0EBA1-9960-42C9-BF9B-60E150B429AE')" />
	<xsl:value-of select="$dataType/@Name" />

*****

### GetDataTypeById
Returns an `XPathNodeIterator` of the specified data-type by Id.<br>
_Returns_: A node-set of the specified data-type

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| dataTypeId | `System.Int32` | |

#### XSLT Example

	<xsl:variable name="dataType" select="ucomponents.cms:GetDataTypeById(-88)" />
	<xsl:value-of select="$dataType/@Name" />

*****

## Document Types

### GetDocumentTypes
Returns an `XPathNodeIterator` of all the document types created in Umbraco.<br>
_Returns_: A node-set of all the document types used within Umbraco.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| includeTabs | `System.Boolean` | _(optional - defaults to `false`)_ |
| includePropertyTypes | `System.Boolean` | _(optional - defaults to `false`)_ |
| includeAllowedTemplates | `System.Boolean` | _(optional - defaults to `false`)_ |

#### XSLT Example

	<ul>
		<xsl:for-each select="ucomponents.cms:GetDocumentTypes()/DocumentType">
			<li>
				<xsl:value-of select="@name" />
			</li>
		</xsl:for-each>
	</ul>

*****

### GetDocumentType
Returns an XPathNodeIterator of the specified document-type.<br>
_Returns_: A node-set of the specified document-type.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| docTypeId | `System.Int32` | |
| includeTabs | `System.Boolean` | |
| includePropertyTypes | `System.Boolean` | |
| includeAllowedTemplates | `System.Boolean` | |

#### XSLT Example

	<xsl:variable name="docType" select="ucomponents.cms:GetDocumentType(1054, false(), true(), false())" />
	<xsl:value-of select="$docType/@name" />

*****

## Languages

### GetLanguages
Returns an `XPathNodeIterator` of all the languages created in Umbraco.<br>
_Returns_: A node-set of all the languages used within Umbraco

#### XSLT Example

	<ul>
		<xsl:for-each select="ucomponents.cms:GetLanguages()/Language">
			<li>
				<xsl:value-of select="@FriendlyName" />
			</li>
		</xsl:for-each>
	</ul>

*****

### GetLanguage
Gets the language by id.<br>
_Returns_: A node-set of the specified language.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| languageId | `System.Int32` | |

#### XSLT Example

	<xsl:variable name="language" select="ucomponents.cms:GetLanguage(1)" />
	<xsl:value-of select="$language/@FriendlyName" />

*****

### GetLanguageByCultureCode
Gets the language by culture code.<br>
_Returns_: Returns a node-set of the specified language.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| cultureCode | `System.String` | |

#### XSLT Example

	<xsl:variable name="language" select="ucomponents.cms:GetLanguageByCultureCode('en-US')" />
	<xsl:value-of select="$language/@FriendlyName" />

*****

### GetLanguageByNodeId
Gets the language by node id.<br>
_Returns_: Returns a node-set of the language by the node id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeId | `System.Int32` | |

#### XSLT Example

	<xsl:variable name="language" select="ucomponents.cms:GetLanguageByNodeId(1059)" />
	<xsl:value-of select="$language/@FriendlyName" />

*****

### GetLanguageIdByNodeId
Gets the language id by node id.<br>
_Returns_: Returns the id of the language by the node id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeId | `System.Int32` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetLanguageIdByNodeId(1059)" />

*****

## Macros

### GetMacros
Returns an `XPathNodeIterator` of all the macros created in Umbraco.<br>
_Returns_: A node-set of all the macros used within Umbraco.


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetMacros()" />
	<ul>
		<xsl:for-each select="ucomponents.cms:GetMacros()/macro">
			<li>
				<xsl:value-of select="@name" />
			</li>
		</xsl:for-each>
	</ul>

*****

### GetMacro
Returns an `XPathNodeIterator` of the specified macro.<br>
_Returns_: A node-set of the specified macro.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| alias | `System.String` | |

#### XSLT Example

	<xsl:variable name="macro" select="ucomponents.cms:GetMacro('Breadcrumb')" />
	<xsl:value-of select="$macro/@name" />

*****

## Media Types

### GetMediaTypes
Returns an `XPathNodeIterator` of all the media types created in Umbraco.<br>
_Returns_: A node-set of all the media types used within Umbraco.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| includeTabs | `System.Boolean` | _(optional - defaults to `false`)_ |
| includePropertyTypes | `System.Boolean` | _(optional - defaults to `false`)_ |

#### XSLT Example

	<ul>
		<xsl:for-each select="ucomponents.cms:GetMediaTypes(false(), false())/MediaType">
			<li>
				<xsl:value-of select="@name" />
			</li>
		</xsl:for-each>
	</ul>

*****

### GetMediaType
Returns an `XPathNodeIterator` of the specified media-type.<br>
_Returns_: A node-set of the specified media-type.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| mediaTypeId | `System.Int32` | |
| includeTabs | `System.Boolean` | |
| includePropertyTypes | `System.Boolean` | |

#### XSLT Example

	<xsl:variable name="mediaType" select="ucomponents.cms:GetMediaType(1032, false(), false())" />
	<xsl:value-of select="$mediaType/@name" />

*****

## Member Types

### GetMemberTypes
Returns an `XPathNodeIterator` of all the member types created in Umbraco.<br>
_Returns_: A node-set of all the member types used within Umbraco.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| includeTabs | `System.Boolean` | _(optional)_ |
| includePropertyTypes | `System.Boolean` | _(optional)_ |

#### XSLT Example

	<ul>
		<xsl:for-each select="ucomponents.cms:GetMemberTypes(false(), false())/MemberType">
			<li>
				<xsl:value-of select="@name" />
			</li>
		</xsl:for-each>
	</ul>

*****

### GetMemberType
Returns an `XPathNodeIterator` of the specified member-type.<br>
_Returns_: A node-set of the specified member-type.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| memberTypeId | `System.Int32` | |
| includeTabs | `System.Boolean` | |
| includePropertyTypes | `System.Boolean` | |

#### XSLT Example

	<xsl:variable name="member" select="ucomponents.cms:GetMemberType(1066, false(), false())" />
	<xsl:value-of select="$member/@name" />

*****

## Templates

### GetTemplates
Gets the templates.<br>
_Returns_: Returns an XML structure of all the templates.


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetTemplates()" />
	<ul>
		<xsl:for-each select="ucomponents.cms:GetTemplates()/Template">
			<li>
				<xsl:value-of select="@Name" />
			</li>
		</xsl:for-each>
	</ul>

*****

### GetTemplateAlias
Gets the template alias.<br>
_Returns_: Returns the alias name of the template.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| templateId | `System.Int32` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetTemplateAlias(1045)" />

*****

### GetTemplateById
Gets the template by id.<br>
_Returns_: Returns an XML structure of the template.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| templateId | `System.Int32` | |

#### XSLT Example

	<xsl:variable name="template" select="ucomponents.cms:GetTemplateAlias(1045)" />
	<xsl:value-of select="$template/@Name" />

*****

### GetTemplateByAlias
Gets the template by alias.<br>
_Returns_: Returns an XML structure of the template.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| templateAlias | `System.String` | |

#### XSLT Example

	<xsl:variable name="template" select="ucomponents.cms:GetTemplateByAlias('Homepage')" />
	<xsl:value-of select="$template/@Name" />

*****

### GetTemplateIdByAlias
Gets the template id by alias.<br>
_Returns_: Returns the template id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| templateAlias | `System.String` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetTemplateIdByAlias('Homepage')" />

*****

## Users

### GetAllUsers
Gets all users.

#### XSLT Example

	<ul>
		<xsl:for-each select="ucomponents.cms:GetAllUsers()/User">
			<li>
				<a href="mailto:{@email}">
					<xsl:value-of select="@name" />
				</a>
			</li>
		</xsl:for-each>
	</ul>

*****

### GetAllUsersByEmail
Gets all users by email.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| email | `System.String` | |

#### XSLT Example

	<ul>
		<xsl:for-each select="ucomponents.cms:GetAllUsersByEmail('admin@domain.com')/User">
			<li>
				<a href="mailto:{@email}">
					<xsl:value-of select="@name" />
				</a>
			</li>
		</xsl:for-each>
	</ul>

*****

### GetAllUsersByLoginName
Gets the name of all users by login.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| loginName | `System.String` | |
| partialMatch | `System.Boolean` | _(optional - defaults to `false`)_ |

#### XSLT Example

	<ul>
		<xsl:for-each select="ucomponents.cms:GetAllUsersByLoginName('admin', false())/User">
			<li>
				<a href="mailto:{@email}">
					<xsl:value-of select="@name" />
				</a>
			</li>
		</xsl:for-each>
	</ul>

*****

### GetUser
Gets the user.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| userId | `System.Int32` | |

#### XSLT Example

	<xsl:variable name="user" select="ucomponents.cms:GetUser(1)" />
	<xsl:value-of select="$user/@name" />

*****

### GetUserEmail
Gets the user email.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| userId | `System.Int32` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUserEmail(1)" />

*****

### GetUserLanguage
Gets the user language.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| userId | `System.Int32` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUserLanguage(1)" />

*****

### GetUserLoginName
Gets the name of the user login.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| userId | `System.Int32` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUserLoginName(1)" />

*****

### GetUserName
Gets the name of the user.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| userId | `System.Int32` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUserName(1)" />

*****

### GetUserTypeAlias
Gets the user type key.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| userId | `System.Int32` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUserTypeAlias(1)" />

*****

## General

### GetContentIdByPropertyId
Gets the Content Id by property Id.<br>
_Returns_: Returns the Content Id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| propertyId | `System.Int32` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetContentIdByPropertyId(2692)" />

*****

### GetDictionaryItem
Gets the dictionary item for the specified language id, with a fall-back default value.<br>
_Returns_: Returns the string value of the dictionary item for the specified language id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| key | `System.String` | |
| languageId | `System.Int32` | |
| defaultValue | `System.String` | _(optional - defaults to `string.Empty`)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetDictionaryItem('[XSLTsearch]Heading-SearchResults', 1, 'Search Results')" />

*****

### GetUniqueId
Gets the unique id of a `CMSNode`.<br>
_Returns_: Returns the unique id of a `CMSNode`.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| id | `System.Int32` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUniqueId($currentPage/@id)" />

*****

### IsLegacyXmlSchema
Checks the Umbraco XML Schema version in use.<br>
_Returns_: `true` if the legacy XML schema is used; otherwise, `false`.

#### XSLT Example

	<xsl:choose>
		<xsl:when test="ucomponents.cms:IsLegacyXmlSchema()">
			<xsl:value-of select="$currentPage/data[@alias = 'pageTitle']" />
		</xsl:when>
		<xsl:otherwise>
			<xsl:value-of select="$currentPage/pageTitle" />
		</xsl:otherwise>
	</xsl:choose>

*****

### InPreviewMode
Determines whether Umbraco front-end is in preview mode.<br>
_Returns_: `true` if Umbraco front-end is in preview mode; otherwise, `false`.

#### XSLT Example

	<xsl:choose>
		<xsl:when test="ucomponents.cms:InPreviewMode()">
			<p>Display something in preview mode.</p>
		</xsl:when>
		<xsl:otherwise>
			<p>Hide something from preview mode.</p>
		</xsl:otherwise>
	</xsl:choose>

*****
