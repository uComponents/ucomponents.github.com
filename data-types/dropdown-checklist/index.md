---
layout: datatype
title: DropDown CheckList
category: Data Types
since_version: 1.0
retired_version: 
---

This is a DropDownList containing CheckBoxes.

## Prevalue Editor Settings

Adding items to control

![Prevalue Editor](PreValueEditor.jpg)

## Content Editor

Using the conrol

![Content Editor](DataEditor.jpg)

## XSLT Example

	<xsl:template match="/">
		<ul>
			<xsl:for-each select="umbraco.library:Split($currentPage/languages[not(@isDoc)], ',')/*">
				<li>
					<xsl:value-of select="."/>
				</li>
			</xsl:for-each>
		</ul>
	</xsl:template>
