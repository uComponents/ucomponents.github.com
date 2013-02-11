---
layout: datatype
title: DataType Grid
category: Data Types
description: DataType Grid is basically a DataType that allows you to store DataTypes in a grid-like fashion. 
Think Excel, but with other Datatypes instead of textboxes.
since_version: 3.0
---

## Prevalue Editor ##

![Prevalue Editor](PreValueEditor.JPG)

### Content Editor Settings ###
**Show Label:** Toggle the left side label for the content editor.    
**Show Grid Header:** Toggle the visibility for the grid header. Also toggles search functionality.    
**Show Grid Footer:** Toggle the visibility for the grid footer. Also toggles paging.    
**Rows Per Page:** How many rows should be shown per page

### Datatype (Column) Settings ###
**Name:** The column name. Can be localized by inserting the dictionary key prepended with a hash (#).    
**Alias:** The column alias. This is the key for the column.   
**DataType:** The editor datatype for the column. See using custom datatypes if you want to use custom (untested) datatypes.
**Mandatory:** Toggles whether a value must be set for this column when inserting or updating a row.   
**Validation:** Custom Regex validation for the column value. Leave blank to disable.    
**Content Sort Priority:** If you want to set a default grid sorting for the content editors, set the column priority here. Leave blank to disable automatic sorting.    
**Content Sort Order:** The grid sorting direction. Only used if Content Sort Priority has been enabled.

## Content Editor ##

### Grid ###
![Content Editor](contenteditor.JPG)

### Add row dialog ###
![Add Row Dialog](insertdialog.JPG)

### Edit row dialog ###
![Edit Row Dialog](editdialog.JPG)

## Compatible Datatypes ##
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
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Numeric</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Simple Editor</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Textstring</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
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
				<em/>
			</td>
		</tr>
		<tr>
			<td>Approved Color</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Checkbox list</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Content Picker</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Date Picker with time</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0.2</td>
			<td align="center" valign="top">
				<em/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Date Picker</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0.2</td>
			<td align="center" valign="top">
				<em/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Dropdown multiple</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0.1</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Folder Browser</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td style="background-color: #ff0000;" align="center" valign="top">
				<span style="color: #ffffff;">YSOD</span>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Dropdown</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0.1</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Member Picker</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0.2</td>
			<td align="center" valign="top">
				<em/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Radiobox</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Related Links</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td style="background-color: #ff0000;" align="center" valign="top">
				<span style="color: #ffffff;">Doesn't add values</span>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Richtext editor</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td style="background-color: #ff0000;" align="center" valign="top">
				<span style="color: #ffffff;">Not shown</span>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Textbox multiple</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Tags</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td style="background-color: #ff0000;" align="center" valign="top">
				<span style="color: #ffffff;">
					<span style="color: #ffffff;">YSOD</span>
				</span>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>True/false</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v3.0</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Ultimate Picker</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td style="background-color: #ff0000;" align="center" valign="top">
				<span style="color: #ffffff;"/>
			</td>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Upload</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td style="background-color: #ff0000;" align="center" valign="top">
				<span style="color: #ffffff;">YSOD</span>
			</td>
			<td align="center" valign="top">
				<em/>
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
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Character Limit</td>
			<td style="background-color: #00ff00;" align="center" valign="top">v4.0</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Checkbox Tree</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
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
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Dropdown CheckList</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Elastic TextBox</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
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
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
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
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>File DropDownList</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>FilePicker</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Image DropDown</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Incremental TextBox</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>JSON Dropdown</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Multi-Node Tree Picker</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
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
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Multiple Dates</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
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
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
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
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Notes</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Radiobutton List with Images</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Related Links with Media</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Render Macro</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
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
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Slider</td>
			<td align="center" valign="top"/>
			<td style="background-color: #ffff00;" align="center" valign="top">
				<p>
					<em>Does not support editing</em>
				</p>
			</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em/>
			</td>
		</tr>
		<tr>
			<td>Styled TextBox</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
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
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>ToggleBox</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
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
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
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
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>Unique Property</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>
				<span style="color: #3e62a6;">URL Picker</span>
			</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>User Picker</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>XPath CheckBoxList</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
		<tr>
			<td>XPath DropDownList</td>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top"/>
			<td align="center" valign="top">
				<em>X</em>
			</td>
		</tr>
	</tbody>
</table>
