---
layout: datatype
title: DataType Grid
category: Data Types
description: DataType Grid is basically a DataType that allows you to store DataTypes in a grid-like fashion. 
Think Excel, but with other Datatypes instead of textboxes.
since_version: 3.0
---

## Table of contents ##
* [Prevalue Editor](#PrevalueEditor)
* [Content Editor](#ContentEditor)
* [Compatible Datatypes](#CompatibleDatatypes)
* [Localization](#Localization)
* [Razor Samples](#RazorSamples)

## <a id="PrevalueEditor"></a>Prevalue Editor ##

![Prevalue Editor](PreValueEditor.JPG)

### Content Editor Settings ###
**Show Label:** Toggle the left side label for the content editor.    
**Show Grid Header:** Toggle the visibility for the grid header. Also toggles search functionality.    
**Show Grid Footer:** Toggle the visibility for the grid footer. Also toggles paging.    
**Rows Per Page:** How many rows should be shown per page

### Datatype (Column) Settings ###
**Name:** The column name. Can be localized by inserting the dictionary key prepended with a hash (#).    
**Alias:** The column alias. This is the key for the column.   
**DataType:** The editor datatype for the column. See [using custom datatypes][UsingCustomDatatypes] if you want to use custom (untested) datatypes.
**Mandatory:** Toggles whether a value must be set for this column when inserting or updating a row.   
**Validation:** Custom Regex validation for the column value. Leave blank to disable.    
**Content Sort Priority:** If you want to set a default grid sorting for the content editors, set the column priority here. Leave blank to disable automatic sorting.    
**Content Sort Order:** The grid sorting direction. Only used if Content Sort Priority has been enabled.

## <a id="ContentEditor"></a> Content Editor ##

### Grid ###
![Content Editor](contenteditor.JPG)

### Add row dialog ###
![Add Row Dialog](insertdialog.JPG)

### Edit row dialog ###
![Edit Row Dialog](editdialog.JPG)

## <a id="CompatibleDatatypes"></a> Compatible Datatypes ##
<table border="0">
  <tbody>
		<tr>
			<th>Umbraco Native Datatypes </th>
			<th>Fully Compatible </th>
			<th>Partially Compatible </th>
			<th>Not Compatible </th>
			<th>Not Tested </th>
		</tr>
		<tr>
			<td>Label</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Numeric</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Simple Editor</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Textstring</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Media Picker</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0.1</td>
			<td align="center" valign="top">
				<p/>
			</td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Approved Color</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Checkbox list</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Content Picker</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Date Picker with time</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0.2</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Date Picker</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0.2</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Dropdown multiple</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0.1</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Folder Browser</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td style="background-color: #ff0000;" align="center" valign="top">
				<span style="color: #ffffff;">YSOD</span>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Dropdown</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0.1</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Member Picker</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0.2</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Radiobox</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Related Links</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td style="background-color: #ff0000;" align="center" valign="top">
				<span style="color: #ffffff;">Doesn't add values</span>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Richtext editor</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td style="background-color: #ff0000;" align="center" valign="top">
				<span style="color: #ffffff;">Not shown</span>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Textbox multiple</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Tags</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td style="background-color: #ff0000;" align="center" valign="top">
				<span style="color: #ffffff;">
					<span style="color: #ffffff;">YSOD</span>
				</span>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>True/false</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Ultimate Picker</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td style="background-color: #ff0000;" align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Upload</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td style="background-color: #ff0000;" align="center" valign="top">
				<span style="color: #ffffff;">YSOD</span>
			</td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<th>Custom Datatypes </th>
			<th>Fully Compatible </th>
			<th>Partially Compatible </th>
			<th>Not Compatible </th>
			<th>Not Tested </th>
		</tr>
		<tr>
			<td>Auto Complete</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v4.0</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Character Limit</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v4.0</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Checkbox Tree</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>
				<span style="color: #000000;">
					<span style="color: #3e62a6;">Country Picker</span>
				</span>
			</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Dropdown CheckList</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Elastic TextBox</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>
				<a href="http://ucomponents.codeplex.com/wikipage?title=Enum CheckBoxList">
					<span style="color: #3e62a6;">Enum CheckBoxList</span>
				</a>
			</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>
				<a href="http://ucomponents.codeplex.com/wikipage?title=Enum DropDownList">
					<span style="color: #3e62a6;">Enum DropDownList </span>
				</a>
			</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>File DropDownList</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>FilePicker</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Image DropDown</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Incremental TextBox</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>JSON Dropdown</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Multi-Node Tree Picker</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>
				<a href="http://ucomponents.codeplex.com/wikipage?title=MultiPickerRelations&amp;referringTitle=DataTypes">
					<span style="color: #3e62a6;">MultiPicker Relations</span>
				</a>
			</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Multiple Dates</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>
				<a href="http://ucomponents.codeplex.com/wikipage?title=MultipleTextstring&amp;referringTitle=Documentation">
					<span style="color: #3e62a6;">Multiple Textstring</span>
				</a>
			</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>
				<a href="http://ucomponents.codeplex.com/wikipage?title=MultiUrlPicker&amp;referringTitle=Documentation">
					<span style="color: #3e62a6;">Multi-URL Picker</span>
				</a>
			</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Notes</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Radiobutton List with Images</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Related Links with Media</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Render Macro</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>
				<a href="http://ucomponents.codeplex.com/wikipage?title=Similarity&amp;referringTitle=Documentation">
					<span style="color: #3e62a6;">Similarity</span>
				</a>
			</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Slider</td>
			<td align="center" valign="top"> </td>
			<td style="background-color: #ffff00;" align="center" valign="top">
				<p>
					<em>Does not support editing</em>
				</p>
			</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em> </em>
			</td>
		</tr>
		<tr>
			<td>Styled TextBox</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>
				<a href="http://ucomponents.codeplex.com/wikipage?title=SQL DropDownList&amp;referringTitle=Documentation">
					<span style="color: #3e62a6;">SQL DropDownList</span>
				</a>
			</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>ToggleBox</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>
				<a href="http://ucomponents.codeplex.com/wikipage?title=TextImage&amp;referringTitle=Documentation">
					<span style="color: #3e62a6;">Text Image</span>
				</a>
			</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>
				<a href="http://ucomponents.codeplex.com/wikipage?title=TextstringArray&amp;referringTitle=Documentation">
					<span style="color: #3e62a6;">Textstring Array</span>
				</a>
			</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Unique Property</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>
				<span style="color: #3e62a6;">URL Picker</span>
			</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>User Picker</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>XPath CheckBoxList</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>XPath DropDownList</td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top"> </td>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
	</tbody>
</table>

### [UsingCustomDatatypes] Using custom datatypes ###
By default, only datatypes that are verified are enabled and selectable from the prevalue editor.
To enable a non-default datatype, go to {your-umbraco-folder}\config and open the file DataTypeGrid.config.

Add your datatype guid to the `<CompatibleDataTypes>` section like this:

    <add guid="6c738306-4c17-4d88-b9bd-6546f3771597"/>
    
Recycle the application pool in IIS or touch the web.config file.
You can now use your datatype with DataType Grid.

## <a id="Localization"></a> Localization ##
DataType Grid is localizable, meaning you can make your own translation using the Dictionary in the Umbraco backoffice.

Please consult the table of aliases below to create your own translation.

### Content Editor ###
<table border="0">
	<tbody>
		<tr>
			<td>
				<strong>Alias</strong>
			</td>
			<td>
				<strong>Default Value</strong>
			</td>
			<td>
				<strong>Description</strong>
			</td>
		</tr>
		<tr>
			<td>Delete</td>
			<td>Delete</td>
			<td>The button tooltip text for deleting a row</td>
		</tr>
		<tr>
			<td>Edit</td>
			<td>Edit</td>
			<td>The button tooltip text for editing a row</td>
		</tr>
		<tr>
			<td>MoveUp</td>
			<td>Move up</td>
			<td>The button tooltip text for moving a row up</td>
		</tr>
		<tr>
			<td>MoveDown</td>
			<td>Move down</td>
			<td>The button tooltip text for moving a row down</td>
		</tr>
		<tr>
			<td>Add</td>
			<td>Add</td>
			<td>The button text for adding a new row (both in the footer and in the dialog)</td>
		</tr>
		<tr>
			<td>Update</td>
			<td>Update</td>
			<td>The button text for updating a row</td>
		</tr>
	</tbody>
</table>

### Prevalue Editor ###
<table border="0">
	<tbody>
		<tr>
			<td>
				<strong>Alias</strong>
			</td>
			<td>
				<strong>Default Value</strong>
			</td>
			<td>
				<strong>Description</strong>
			</td>
		</tr>
		<tr>
			<td>AddNewDataType</td>
			<td>Add new datatype</td>
			<td>The title text for the "add new datatype" form</td>
		</tr>
		<tr>
			<td>Error</td>
			<td>Error</td>
			<td>The error title for the "add new datatype" form</td>
		</tr>
		<tr>
			<td>Name</td>
			<td>Name</td>
			<td>The name label for the column name</td>
		</tr>
		<tr>
			<td>YouMustSpecifyAName</td>
			<td>You must specify a name</td>
			<td>The error message shown if you didn't specify a name for the column when saving the datatype</td>
		</tr>
		<tr>
			<td>Alias</td>
			<td>Alias</td>
			<td>The alias label for the column alias</td>
		</tr>
		<tr>
			<td>YouMustSpecifyAnAlias</td>
			<td>You must specify an alias</td>
			<td>The error message shown if you didn't specify an alias for the column when saving the datatype</td>
		</tr>
		<tr>
			<td>AliasAlreadyExists</td>
			<td>Alias already exists!</td>
			<td>The error Message shown if the alias you entered already exists</td>
		</tr>
		<tr>
			<td>DataType</td>
			<td>DataType</td>
			<td>The label for the column datatype</td>
		</tr>
		<tr>
			<td>Validation</td>
			<td>Validation</td>
			<td>The label for the column validation string</td>
		</tr>
		<tr>
			<td>SearchForARegularExpression</td>
			<td>Search for a regular expression</td>
			<td>The label for the link that opens a window where you can find regular expressions</td>
		</tr>
		<tr>
			<td>ValidationStringIsNotValid</td>
			<td>Validation string is not valid</td>
			<td>The error Message shown if the validation regex is not valid</td>
		</tr>
		<tr>
			<td>ContentSortPriority</td>
			<td>Content Sort Priority</td>
			<td>The label text for the column sort priority</td>
		</tr>
		<tr>
			<td>ContentSortOrder</td>
			<td>Content Sort Order</td>
			<td>The label text for the column sort order</td>
		</tr>
		<tr>
			<td>Ascending</td>
			<td>Ascending</td>
			<td>The dropdown item text for ascending sort order</td>
		</tr>
		<tr>
			<td>Descending</td>
			<td>Descending</td>
			<td>The dropdown item text for descending sort order</td>
		</tr>
		<tr>
			<td>Type</td>
			<td>Type</td>
			<td>The title text for the "edit datatype" form</td>
		</tr>
		<tr>
			<td>AreYouSureYouWantToDeleteThisColumn</td>
			<td>Are you sure you want to delete this column</td>
			<td>The dialog text shown when trying to delete a column</td>
		</tr>
	</tbody>
</table>

## <a id="RazorSamples"></a> Razor Samples ##

### Getting DataTypeGrid values ###

#### Pre v5.4.0 ####
This example uses a document type that has the following DTG datatype:
![Prevalue Editor](prevalueeditor.JPG)

It was then populated with the following values:
![Content Editor](contenteditor.JPG)
![Add Row Dialog](insertdialog.JPG)

To get out those values using Razor syntax, you can use the following code:

	@*
	DataType Grid Sample
	=================================
	This snippet makes lists all values stored in a DataType Grid
	NOTE: The property value is of type DynamicXML.
	      All DynamicXML properties are case-sensitive!
	
	NOTE: It is safe to remove this comment (anything between @ * * @), the code that generates the list is only the below!
	*@
	
	@inherits umbraco.MacroEngines.DynamicNodeContext
	@using uComponents.Core
	@using umbraco.cms.businesslogic.datatype
	
	<p>Property XML:<br/>@Model.DataTypeGrid.ToXml()</p>
	
	<ul>
	    @foreach(var item in Model.DataTypeGrid) {
	        @* Inside here, everything is case-sensitive *@
	        <li>ID: @item.id
	            <table>
	                <tr>
	                    <th>XML</th>
	                    <td>@item.ToXml()</td>
	                </tr>
	                <tr>
	                    <th>Image</th>
	                    <td><img src="@Library.MediaById(int.Parse(item.image.InnerText)).UmbracoFile" width="100" height="100"/></td>
	                </tr>
	                <tr>
	                    <th>Dropdown List</th>
	                    <td>
	                        <ul>
	                        @* Display prevalue name instead of id *@
	                        @{ IList<PreValue> preValues1 = uQuery.GetPreValues(int.Parse(item.list.nodeType)); }
	                        @foreach(var i in item.list.InnerText.Split(',')) {
	                            <li>@preValues1.Single(x => x.Id.ToString() == i).Value (#@i)</li>
	                        }
	                        </ul>
	                    </td>
	                </tr>
	                <tr>
	                    <th>Dropdown Multi</th>
	                    <td>
	                        <ul>
	                        @* Display prevalue name instead of id *@
	                        @{ IList<PreValue> preValues2 = uQuery.GetPreValues(int.Parse(item.multiList.nodeType)); }
	                        @foreach(var i in item.multiList.InnerText.Split(',')) {
	                            <li>@preValues2.Single(x => x.Id.ToString() == i).Value (#@i)</li>
	                        }
	                        </ul>
	                    </td>
	                </tr>
	                <tr>
	                    <th>Dropdown List</th>
	                    <td>
	                        <ul>
	                        @* Display prevalue name instead of id *@
	                        @{ IList<PreValue> preValues3 = uQuery.GetPreValues(int.Parse(item.meh.nodeType)); }
	                        @foreach(var i in item.meh.InnerText.Split(',')) {
	                            <li>@preValues3.Single(x => x.Id.ToString() == i).Value (#@i)</li>
	                        }
	                        </ul>
	                    </td>
	                </tr>
	            </table>
	        </li>
	    }
	</ul>

This should give you the following output:
![Razor Output Pre v5.4.0](RazorSampleOutput_pre54.JPG)

#### v5.4.0 -> current ####
