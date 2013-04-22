---
layout: datatype
title: Static File Macro Engine
category: Macro Engines
since_version: 4.1.0
---

The Static File Macro Engine is a custom macro engine used to render static files, (e.g. HTML or plain-text) from a file location.

## External file location

An example of this would be if you had static HTML files on your server that you wanted to pull into your templates, (e.g. Google Analytics code snippet)

	<umbraco:Macro runat="server" Language="html" FileLocation="/GoogleAnalytics.html" />

Or if you wanted to display the contents of your `robots.txt` file? (for whatever reason) :-)

	<div>
		<h1>My robots.txt!</h1>
		<pre><umbraco:Macro runat="server" Language="txt" FileLocation="/robots.txt" /></pre>
	</div>

## Inline snippet

	<umbraco:Macro runat="server" Language="html">
		Hello World!
	</umbraco:Macro>

We're not sure why you would ever want to use this, but the Macro Engine does support this.
