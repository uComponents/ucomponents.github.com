---
layout: datatypesubpage
title: Razor Samples
category: DataType Grid
description: DataType Grid is basically a DataType that allows you to store DataTypes in a grid-like fashion. Think Excel, but with other Datatypes instead of textboxes.
since_version: 3.0
sidebar: <h3>Table of contents</h3>
    <ul>
        <li><a href="../">Usage</a></li>
        <li><a href="../compatible-datatypes">Compatible Datatypes</a></li>
        <li><a href="../localization">Localization</a></li>
        <li>Razor Samples</li>
        <li><a href="../integration">Integration</a></li>
    </ul>
---
### Getting DataTypeGrid values ###

#### v5.4.0 ####

This example uses a document type that has the following DTG datatype:

<img src="../PreValueEditor_post54.JPG" width="700" alt="Prevalue Editor"/>    
    
    
It was then populated with the following values:
    
<img alt="Content Editor" src="../contenteditor_post54.JPG" width="700"/>    


<img alt="Add Row Dialog" src="../insertdialog_post54.JPG" width="400"/>    
    
    
To get out those values using Razor syntax, you can use the following code:

	@inherits umbraco.MacroEngines.DynamicNodeContext
		
	<h3>Show raw data</h3>
	<p>@Model.DataTypeGrid</p>
		
	<h3>List all rows and cells</h3>
	<table cellspacing="0" cellpadding="0">
		<tr>
			<th>Row ID</th>
			<th>Row SortOrder</th>
			<th>Row Cells</th>
		</tr>
		@foreach(var row in Model.DataTypeGrid) {
			<tr>
				<th>@row.Id</th>
				<th>@row.SortOrder</th>
				<td>
					<table cellspacing="0" cellpadding="0">
						<tr>
							<th>Cell Alias</th>
							<th>Cell Name</th>
							<th>Cell DataType</th>
							<th>Cell Value</th>
						</tr>
						@foreach(var cell in row) {
							<tr>
								<td>@cell.Alias</td>
								<td>@cell.Name</td>
								<td>@cell.DataType</td>
								<td>@cell.Value</td>
							</tr>
						}
					</table>
				</td>
			</tr>
		}
	</table>
		
	<h3>Alternate access</h3>
	<table cellspacing="0" cellpadding="0">
		<tr>
			<th>Get cell value by key (alias)</th>
			<td>@Html.Raw("@Model.DataTypeGrid[0][\"image\"]")</td>
			<td>@Model.DataTypeGrid[0]["image"]</td>
		</tr>
		<tr>
			<th>Get cell value by key (alias) using dynamic access</th>
			<td>@Html.Raw("@Model.DataTypeGrid[0].image")</td>
			<td>@Model.DataTypeGrid[0].image</td>
		</tr>
		<tr>
			<th>Get cell value by name using dynamic access</th>
			<td>@Html.Raw("@Model.DataTypeGrid[0].Image")</td>
			<td>@Model.DataTypeGrid[0].Image</td>
		</tr>
	</table>
    	
    
This should give you the following output:    

<img src="../RazorSampleOutput_post54.JPG" width="500"/>

#### Up until v5.4.0 ####
This example uses a document type that has the following DTG datatype:
    
<img src="../PreValueEditor_pre54.JPG" width="700" alt="Prevalue Editor"/>    

    
It was then populated with the following values:
    
<img alt="Content Editor" src="../contenteditor_pre54.JPG" width="700"/>    


<img alt="Add Row Dialog" src="../insertdialog_pre54.JPG" width="400"/>    

    
To get out those values using Razor syntax, you can use the following code:
	
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
    
<img src="../RazorSampleOutput_pre54.JPG" width="500"/>