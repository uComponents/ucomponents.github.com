---
layout: datatype
title: XSLT Macro Engine
category: Macro Engines
since_version: 4.1.0
---

XSLT Macro Engine is a custom macro engine used to render inline XSLT code snippets or external XSLT file locations.

## Inline code snippet

	<umbraco:Macro runat="server" Language="xslt">
		<xsl:value-of select="$currentPage/@nodeName" />
	</umbraco:Macro>

## External file location

	<umbraco:Macro runat="server" Language="xslt" FileLocation="xslt/MyAwesomeNavigation.xslt" />


## Screencast

<iframe src="http://www.screenr.com/embed/Rf9" width="650" height="396" frameborder="0"></iframe>


## Origin

The XSLT Macro Engine original started as a separate project, (see [Our Umbraco for details](http://our.umbraco.org/projects/backoffice-extensions/xslt-macro-engine).)
