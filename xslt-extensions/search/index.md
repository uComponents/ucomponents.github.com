---
layout: extension
title: Search
category: XSLT Extensions
since_version: 2.1
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Search" alias="ucomponents.search" />
		...
	</XsltExtensions>

*****

## Methods
Here are available methods in the ```Search``` library:

* [AdvancedSearch](#advancedsearch)
* [AdvancedSearch](#advancedsearch)
* [AdvancedSearch](#advancedsearch)
* [AdvancedSearch](#advancedsearch)
* [GetNodeIds](#getnodeids)
* [GetNodeIds](#getnodeids)
* [GetNodeIds](#getnodeids)
* [QuickSearch](#quicksearch)
* [QuickSearch](#quicksearch)
* [QuickSearch](#quicksearch)
* [RawQuery](#rawquery)
* [InternalSearch](#internalsearch)
* [GetResultsAsXml](#getresultsasxml)

*****

### AdvancedSearch
Performs an advanced search against an Examine/Lucene index.
_Returns_: Returns an XML structure of the advanced search results.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| searchText | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:AdvancedSearch(searchText)" />


*****

### AdvancedSearch
Performs an advanced search against an Examine/Lucene index.
_Returns_: Returns an XML structure of the advanced search results.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| searchText | ```System.String``` | |
| useWildcards | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:AdvancedSearch(searchText, useWildcards)" />


*****

### AdvancedSearch
Advanceds the search.
_Returns_: Returns an XML structure of the advanced search results.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| searchText | ```System.String``` | |
| useWildcards | ```System.Boolean``` | |
| providerName | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:AdvancedSearch(searchText, useWildcards, providerName)" />


*****

### AdvancedSearch
Performs an advanced search against an Examine/Lucene index.
_Returns_: Returns an XML structure of the advanced search results.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| searchText | ```System.String``` | |
| useWildcards | ```System.Boolean``` | |
| providerName | ```System.String``` | |
| indexType | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:AdvancedSearch(searchText, useWildcards, providerName, indexType)" />


*****

### GetNodeIds
Gets the node ids.
_Returns_: Returns a CSV of node Ids from a basic/quick search

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| searchText | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:GetNodeIds(searchText)" />


*****

### GetNodeIds
Gets the node ids.
_Returns_: Returns a CSV of node Ids from a basic/quick search

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| searchText | ```System.String``` | |
| useWildcards | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:GetNodeIds(searchText, useWildcards)" />


*****

### GetNodeIds
Gets the node ids.
_Returns_: Returns a CSV of node Ids from a basic/quick search

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| searchText | ```System.String``` | |
| useWildcards | ```System.Boolean``` | |
| providerName | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:GetNodeIds(searchText, useWildcards, providerName)" />


*****

### QuickSearch
Performs a basic/quick search against an Examine/Lucene index.
_Returns_: Returns an XML structure of the basic/quick search results.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| searchText | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:QuickSearch(searchText)" />


*****

### QuickSearch
Performs a basic/quick search against an Examine/Lucene index.
_Returns_: Returns an XML structure of the basic/quick search results.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| searchText | ```System.String``` | |
| useWildcards | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:QuickSearch(searchText, useWildcards)" />


*****

### QuickSearch
Performs a basic/quick search against an Examine/Lucene index.
_Returns_: Returns an XML structure of the basic/quick search results.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| searchText | ```System.String``` | |
| useWildcards | ```System.Boolean``` | |
| providerName | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:QuickSearch(searchText, useWildcards, providerName)" />


*****

### RawQuery
Performs a raw query against the specified Examine/Lucene provider.
_Returns_: Returns an XML structure of the raw search query results.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| rawQuery | ```System.String``` | |
| useWildcards | ```System.Boolean``` | |
| providerName | ```System.String``` | |
| indexType | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:RawQuery(rawQuery, useWildcards, providerName, indexType)" />


*****

### InternalSearch
Perform a search (interally).

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| searchText | ```System.String``` | |
| useWildcards | ```System.Boolean``` | |
| providerName | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:InternalSearch(searchText, useWildcards, providerName)" />


*****

### GetResultsAsXml
Gets the results as XML.
_Returns_: Returns an XML structure of the search results.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| results | ```Examine.ISearchResults``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.search:GetResultsAsXml(results)" />


*****

