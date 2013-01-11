---
layout: extension
title: Cms
category: XSLT Extensions
since_version: 1.0
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Cms" alias="ucomponents.cms" />
		...
	</XsltExtensions>

*****

## Methods
Here are available methods in the ```Cms``` library:

* [AppendContentType](#appendcontenttype)
* [AppendDocumentType](#appenddocumenttype)
* [AppendMediaType](#appendmediatype)
* [AppendMemberType](#appendmembertype)
* [GetAllTemplates](#getalltemplates)
* [GetAllUsers](#getallusers)
* [GetAllUsersByEmail](#getallusersbyemail)
* [GetAllUsersByLoginName](#getallusersbyloginname)
* [GetAllUsersByLoginName](#getallusersbyloginname)
* [GetUser](#getuser)
* [GetUserEmail](#getuseremail)
* [GetUserLanguage](#getuserlanguage)
* [GetUserLoginName](#getuserloginname)
* [GetUserName](#getusername)
* [GetUserTypeAlias](#getusertypealias)
* [ConvertUsersToXml](#convertuserstoxml)
* [AppendUser](#appenduser)
* [GetLanguages](#getlanguages)
* [GetLanguage](#getlanguage)
* [GetLanguageByCultureCode](#getlanguagebyculturecode)
* [GetLanguageByNodeId](#getlanguagebynodeid)
* [GetLanguageIdByNodeId](#getlanguageidbynodeid)
* [GetDocumentTypes](#getdocumenttypes)
* [GetDocumentTypes](#getdocumenttypes)
* [GetDocumentType](#getdocumenttype)
* [GetMediaTypes](#getmediatypes)
* [GetMediaTypes](#getmediatypes)
* [GetMediaType](#getmediatype)
* [GetMemberTypes](#getmembertypes)
* [GetMemberTypes](#getmembertypes)
* [GetMemberType](#getmembertype)
* [GetMacros](#getmacros)
* [GetMacro](#getmacro)
* [GetDataTypes](#getdatatypes)
* [GetDataTypeByGuid](#getdatatypebyguid)
* [GetDataTypeById](#getdatatypebyid)
* [GetTemplates](#gettemplates)
* [GetTemplateAlias](#gettemplatealias)
* [GetTemplateById](#gettemplatebyid)
* [GetTemplateByAlias](#gettemplatebyalias)
* [GetTemplateIdByAlias](#gettemplateidbyalias)
* [GetContentIdByPropertyId](#getcontentidbypropertyid)
* [GetDictionaryItem](#getdictionaryitem)
* [GetDictionaryItem](#getdictionaryitem)
* [GetUniqueId](#getuniqueid)
* [IsLegacyXmlSchema](#islegacyxmlschema)
* [InPreviewMode](#inpreviewmode)

*****

### AppendContentType
Appends the type of the content.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| xd | ```System.Xml.XmlDocument``` | |
| elementName | ```System.String``` | |
| contentType | ```umbraco.cms.businesslogic.ContentType``` | |
| includeTabs | ```System.Boolean``` | |
| includePropertyTypes | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:AppendContentType(xd, elementName, contentType, includeTabs, includePropertyTypes)" />


*****

### AppendDocumentType
Appends the type of the document.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| xd | ```System.Xml.XmlDocument``` | |
| docType | ```umbraco.cms.businesslogic.web.DocumentType``` | |
| includeTabs | ```System.Boolean``` | |
| includePropertyTypes | ```System.Boolean``` | |
| includeAllowedTemplates | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:AppendDocumentType(xd, docType, includeTabs, includePropertyTypes, includeAllowedTemplates)" />


*****

### AppendMediaType
Appends the type of the media.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| xd | ```System.Xml.XmlDocument``` | |
| mediaType | ```umbraco.cms.businesslogic.media.MediaType``` | |
| includeTabs | ```System.Boolean``` | |
| includePropertyTypes | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:AppendMediaType(xd, mediaType, includeTabs, includePropertyTypes)" />


*****

### AppendMemberType
Appends the type of the member.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| xd | ```System.Xml.XmlDocument``` | |
| memberType | ```umbraco.cms.businesslogic.member.MemberType``` | |
| includeTabs | ```System.Boolean``` | |
| includePropertyTypes | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:AppendMemberType(xd, memberType, includeTabs, includePropertyTypes)" />


*****

### GetAllTemplates
Gets all templates.
_Returns_: Returns a list of templates.


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetAllTemplates()" />


*****

### GetAllUsers
Gets all users.


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetAllUsers()" />


*****

### GetAllUsersByEmail
Gets all users by email.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| email | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetAllUsersByEmail(email)" />


*****

### GetAllUsersByLoginName
Gets the name of all users by login.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| loginName | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetAllUsersByLoginName(loginName)" />


*****

### GetAllUsersByLoginName
Gets the name of all users by login.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| loginName | ```System.String``` | |
| partialMatch | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetAllUsersByLoginName(loginName, partialMatch)" />


*****

### GetUser
Gets the user.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| userId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUser(userId)" />


*****

### GetUserEmail
Gets the user email.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| userId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUserEmail(userId)" />


*****

### GetUserLanguage
Gets the user language.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| userId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUserLanguage(userId)" />


*****

### GetUserLoginName
Gets the name of the user login.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| userId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUserLoginName(userId)" />


*****

### GetUserName
Gets the name of the user.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| userId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUserName(userId)" />


*****

### GetUserTypeAlias
Gets the user type key.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| userId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUserTypeAlias(userId)" />


*****

### ConvertUsersToXml
Converts the users to XML.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| users | ```umbraco.BusinessLogic.User[]``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:ConvertUsersToXml(users)" />


*****

### AppendUser
Appends the user to the XML document.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| xd | ```System.Xml.XmlDocument``` | |
| user | ```umbraco.BusinessLogic.User``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:AppendUser(xd, user)" />


*****

### GetLanguages
Returns an XPathNodeIterator of all the languages created in Umbraco.
_Returns_: A node-set of all the languages used within Umbraco


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetLanguages()" />


*****

### GetLanguage
Gets the language by id.
_Returns_: A node-set of the specified language.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| languageId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetLanguage(languageId)" />


*****

### GetLanguageByCultureCode
Gets the language by culture code.
_Returns_: Returns a node-set of the specified language.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| cultureCode | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetLanguageByCultureCode(cultureCode)" />


*****

### GetLanguageByNodeId
Gets the language by node id.
_Returns_: Returns a node-set of the language by the node id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetLanguageByNodeId(nodeId)" />


*****

### GetLanguageIdByNodeId
Gets the language id by node id.
_Returns_: Returns the id of the language by the node id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| nodeId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetLanguageIdByNodeId(nodeId)" />


*****

### GetDocumentTypes
Returns an XPathNodeIterator of all the document types created in Umbraco.
_Returns_: A node-set of all the document types used within Umbraco.


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetDocumentTypes()" />


*****

### GetDocumentTypes
Returns an XPathNodeIterator of all the document types created in Umbraco.
_Returns_: A node-set of all the document types used within Umbraco.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| includeTabs | ```System.Boolean``` | |
| includePropertyTypes | ```System.Boolean``` | |
| includeAllowedTemplates | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetDocumentTypes(includeTabs, includePropertyTypes, includeAllowedTemplates)" />


*****

### GetDocumentType
Returns an XPathNodeIterator of the specified document-type.
_Returns_: A node-set of the specified document-type.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| docTypeId | ```System.Int32``` | |
| includeTabs | ```System.Boolean``` | |
| includePropertyTypes | ```System.Boolean``` | |
| includeAllowedTemplates | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetDocumentType(docTypeId, includeTabs, includePropertyTypes, includeAllowedTemplates)" />


*****

### GetMediaTypes
Returns an XPathNodeIterator of all the media types created in Umbraco.
_Returns_: A node-set of all the media types used within Umbraco.


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetMediaTypes()" />


*****

### GetMediaTypes
Returns an XPathNodeIterator of all the media types created in Umbraco.
_Returns_: A node-set of all the media types used within Umbraco.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| includeTabs | ```System.Boolean``` | |
| includePropertyTypes | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetMediaTypes(includeTabs, includePropertyTypes)" />


*****

### GetMediaType
Returns an XPathNodeIterator of the specified media-type.
_Returns_: A node-set of the specified media-type.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| mediaTypeId | ```System.Int32``` | |
| includeTabs | ```System.Boolean``` | |
| includePropertyTypes | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetMediaType(mediaTypeId, includeTabs, includePropertyTypes)" />


*****

### GetMemberTypes
Returns an XPathNodeIterator of all the member types created in Umbraco.
_Returns_: A node-set of all the member types used within Umbraco.


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetMemberTypes()" />


*****

### GetMemberTypes
Returns an XPathNodeIterator of all the member types created in Umbraco.
_Returns_: A node-set of all the member types used within Umbraco.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| includeTabs | ```System.Boolean``` | |
| includePropertyTypes | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetMemberTypes(includeTabs, includePropertyTypes)" />


*****

### GetMemberType
Returns an XPathNodeIterator of the specified member-type.
_Returns_: A node-set of the specified member-type.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| memberTypeId | ```System.Int32``` | |
| includeTabs | ```System.Boolean``` | |
| includePropertyTypes | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetMemberType(memberTypeId, includeTabs, includePropertyTypes)" />


*****

### GetMacros
Returns an XPathNodeIterator of all the macros created in Umbraco.
_Returns_: A node-set of all the macros used within Umbraco.


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetMacros()" />


*****

### GetMacro
Returns an XPathNodeIterator of the specified macro.
_Returns_: A node-set of the specified macro.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| alias | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetMacro(alias)" />


*****

### GetDataTypes
Returns an XPathNodeIterator of all the data types created in Umbraco.
_Returns_: A node-set of all the data types used within Umbraco.


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetDataTypes()" />


*****

### GetDataTypeByGuid
Returns an XPathNodeIterator of the specified data-type by guid.
_Returns_: A node-set of the specified data-type

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| dataTypeGuid | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetDataTypeByGuid(dataTypeGuid)" />


*****

### GetDataTypeById
Returns an XPathNodeIterator of the specified data-type by Id.
_Returns_: A node-set of the specified data-type

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| dataTypeId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetDataTypeById(dataTypeId)" />


*****

### GetTemplates
Gets the templates.
_Returns_: Returns an XML structure of all the templates.


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetTemplates()" />


*****

### GetTemplateAlias
Gets the template alias.
_Returns_: Returns the alias name of the template.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| templateId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetTemplateAlias(templateId)" />


*****

### GetTemplateById
Gets the template by id.
_Returns_: Returns an XML structure of the template.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| templateId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetTemplateById(templateId)" />


*****

### GetTemplateByAlias
Gets the template by alias.
_Returns_: Returns an XML structure of the template.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| templateAlias | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetTemplateByAlias(templateAlias)" />


*****

### GetTemplateIdByAlias
Gets the template id by alias.
_Returns_: Returns the template id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| templateAlias | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetTemplateIdByAlias(templateAlias)" />


*****

### GetContentIdByPropertyId
Gets the Content Id by property Id.
_Returns_: Returns the Content Id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| propertyId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetContentIdByPropertyId(propertyId)" />


*****

### GetDictionaryItem
Gets the dictionary item for the specified language id.
_Returns_: Returns the string value of the dictionary item for the specified language id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| key | ```System.String``` | |
| languageId | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetDictionaryItem(key, languageId)" />


*****

### GetDictionaryItem
Gets the dictionary item for the specified language id, with a fall-back default value.
_Returns_: Returns the string value of the dictionary item for the specified language id.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| key | ```System.String``` | |
| languageId | ```System.Int32``` | |
| defaultValue | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetDictionaryItem(key, languageId, defaultValue)" />


*****

### GetUniqueId
Gets the unique id of a CMSNode.
_Returns_: Returns the unique id of a CMSNode.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| id | ```System.Int32``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.cms:GetUniqueId(id)" />


*****

### IsLegacyXmlSchema
Checks the Umbraco XML Schema version in use
_Returns_: true if [is legacy XML schema]; otherwise, false.


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:IsLegacyXmlSchema()" />


*****

### InPreviewMode
Determines whether Umbraco front-end [is in preview mode].
_Returns_: true if Umbraco front-end [is in preview mode]; otherwise, false.


#### XSLT Example

	<xsl:value-of select="ucomponents.cms:InPreviewMode()" />


*****

