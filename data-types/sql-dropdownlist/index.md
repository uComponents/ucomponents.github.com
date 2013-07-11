---
layout: datatype
title: SQL DropDownList
category: Data Types
description: Use a SQL statement to select the text and values for DropDownList options.
since_version: 3.0
retired_version: 
---

## Prevalue Editor Settings

![Prevalue Editor](PreValueEditor.jpg)


The **SQL Expression** must return two columns: a _'Text'_ field that's used for the visible text and a _'Value'_ field that's used to identify an item. The parameter (or token) @currentId can be used in the SQL, and will be substituted with the id of the Document / Media or Member that the datatype is a property on.

The **Connection string** is configured via a drop down selection, which defaults to the current Umbraco database. If there are connection strings defined in the web.config, these become selectable options. (The connection string name is stored, so migration between environments can all be controlled via the web.config)


	<configuration>
		<connectionStrings>
			<add name="" connectionString="server=;database=;user id=;password=" />
		</connectionStrings>
	</configuration>
_Note: Prior to release v5.0.0 the full connection string value was stored rather than the name to a web.config setting_


## Content Editor
