---
layout: extension
title: Members
category: XSLT Extensions
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Members" alias="ucomponents.members" />
		...
	</XsltExtensions>

## Methods
Here are available methods:

### GetMembersByCsv
Gets the members by CSV.
_Returns_: Returns an XPathNodeIterator of the member nodes from the CSV list.

#### Parameters
| Name | Type |
|------|------|
| csv | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.members:GetMembersByCsv(csv)" />


*****

### GetMembersByGroupName
Gets the usernames of all the members in the specified group.
_Returns_: Returns a list of all the member names.

#### Parameters
| Name | Type |
|------|------|
| groupName | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.members:GetMembersByGroupName(groupName)" />


*****

### GetMembersByType
Gets the members by node type alias.
_Returns_: Returns an XPathNodeIterator of the member nodes from specified node type alias.

#### Parameters
| Name | Type |
|------|------|
| nodeTypeAlias | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.members:GetMembersByType(nodeTypeAlias)" />


*****

### GetMembersByXPath
Gets the members by an XPath expression.
_Returns_: Returns an XPathNodeIterator of the member nodes from specified XPath expression.

#### Parameters
| Name | Type |
|------|------|
| xpath | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.members:GetMembersByXPath(xpath)" />


*****

### GetPublishedXml
Gets the published Xml.
_Returns_: Returns an XPathNodeIterator of all the member nodes.


#### XSLT Example

	<xsl:value-of select="ucomponents.members:GetPublishedXml()" />


*****

### GetUniqueId
Gets the unique id of a member node.
_Returns_: Returns the unique id of a member node.

#### Parameters
| Name | Type |
|------|------|
| memberId | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.members:GetUniqueId(memberId)" />


*****

### IsMemberOfAGroup
Checks if a member is member of a specific group.
_Returns_: Returns true if member is a member of the group.

#### Parameters
| Name | Type |
|------|------|
| groupName | System.String |
| memberId | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.members:IsMemberOfAGroup(groupName, memberId)" />


*****

### GetGroupsByMemberId
Gets a list of group names from the specific member.
_Returns_: A node-set of all the member-groups from the specific member

#### Parameters
| Name | Type |
|------|------|
| memberId | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.members:GetGroupsByMemberId(memberId)" />


*****

### Search
Performs a basic/quick search against the Examine/Lucene index for Members.
_Returns_: Returns an XML structure of the Members search results.

#### Parameters
| Name | Type |
|------|------|
| searchText | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.members:Search(searchText)" />


*****

### Search
Performs a basic/quick search against the Examine/Lucene index for Members.
_Returns_: Returns an XML structure of the Members search results.

#### Parameters
| Name | Type |
|------|------|
| searchText | System.String |
| useWildcards | System.Boolean |

#### XSLT Example

	<xsl:value-of select="ucomponents.members:Search(searchText, useWildcards)" />


*****

