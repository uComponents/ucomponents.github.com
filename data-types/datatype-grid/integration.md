---
layout: datatypesubpage
title: Integration
description: DataType Grid is basically a DataType that allows you to store DataTypes in a grid-like fashion. Think Excel, but with other Datatypes instead of textboxes. 
category: DataType Grid
excerpt: How to do advanced stuff with Datatype Grid.
since_version: 3.0
sidebar: <h4>Table of contents</h4>
    <ul>
        <li><a href="../">Usage</a></li>
        <li><a href="../compatible-datatypes">Compatible Datatypes</a></li>
        <li><a href="../localization">Localization</a></li>
        <li><a href="../razor-samples">Razor Samples</a></li>
        <li>Integration</li>
    </ul>
---
### Manipulate data from code ###
<span class="versions">
	<strong>Versions:</strong>
	<span class="badge badge-warning">5.4.2</span>
	<span class="badge badge-warning">5.5.x</span>
	<span class="badge badge-warning">6.0.x</span>
</span>

#### Example ####

	// Get reference to content
	var contentService = UmbracoContext.Current.Application.Services.ContentService;
	var content = contentService.GetById(Model.CurrentPage.Id);

	// Get original data
	var data = new GridRowCollection(content.GetValue("dataTypeGrid").ToString());

	// Change data
	foreach (var row in data)
	{
	    var cell = row.GetCell("test");
	    cell.Value = new Random().Next(0, 10).ToString();
	}

	content.SetValue("dataTypeGrid", data.ToString());

	// Save content
	var result = contentService.SaveAndPublish(content);


### Creating custom datatype handlers ###
<span class="versions">
	<strong>Versions:</strong>
	<span class="badge badge-warning">6.0.x</span>
</span>

From version `6.0.0` and upwards, it is now possible to create your own datatype handlers for `DataType Grid`.
These handlers allow you to customize how values are displayed in the grid, as well as hooking into the `Save`, `Configure` and `Initialize` events for each datatype.
[There are already handlers in place for most of Umbraco's built-in properties](https://ucomponents.codeplex.com/SourceControl/latest#uComponents.DataTypes/DataTypeGrid/Handlers/DataTypes/) but these can also be overriden.  


#### Example ####
Start out by making a class that is deriving from `uComponents.DataTypes.DataTypeGrid.Handlers.DataTypes.BaseDataTypeHandler<T>`.
Swap `T` with the class name of the datatype you want to handle (see [List of known datatypes](/data-types/datatype-grid/list-of-known-datatypes) for reference).  
You can also (optionally) decorate your property with the `DataTypeHandler` attribute to set priority for your handler.
The default priority for a datatype handler is `0`, and all built-in handlers have priority `-1`.
This means that if you don't add the attribute, the default priority will be applied.

    [DataTypeHandler(Priority = 123]
    public class ContentPickerDataTypeHandler : BaseDataTypeHandler<PagePickerDataType>
    {
        /// <summary>
        /// Method for customizing the way the <see cref="T">datatype</see> value is displayed in the grid.
        /// </summary>
        /// <remarks>Called when the grid displays the cell value for the specified <see cref="T">datatype</see>.</remarks>
        /// <param name="dataType">The <see cref="T">datatype</see> instance.</param>
        /// <returns>The display value.</returns>
        public override string GetDisplayValue(T dataType)
        {
            return base.GetDisplayValue(dataType);
        }

        /// <summary>
        /// Method for getting the typed backing object for the specified <typeparamref name="T">datatype</typeparamref>.
        /// </summary>
        /// <typeparam name="TBackingObjectType">The backing object type.</typeparam>
        /// <param name="dataType">The <typeparamref name="T">datatype</typeparamref> instance.</param>
        /// <returns>The backing object.</returns>
        /// <remarks>Called when the method <see cref="GridCell.GetPropertyValue" /> method is called on a <see cref="GridCell" />.</remarks>
        public override TBackingObjectType GetPropertyValue<TBackingObjectType>(T dataType)
        {
            return base.GetPropertyValue<TBackingObjectType>(dataType);
        }

        /// <summary>
        /// Method for getting the backing object for the specified <see cref="T">datatype</see>.
        /// </summary>
        /// <param name="dataType">The <see cref="T">datatype</see> instance.</param>
        /// <returns>The backing object.</returns>
        /// <remarks>Called when the method <see cref="GridCell.GetPropertyValue()" /> method is called on a <see cref="GridCell" />.</remarks>
        public override object GetPropertyValue(T dataType)
        {
            return base.GetPropertyValue(dataType);
        }

        /// <summary>
        /// Method for getting the control to use when validating the specified <see cref="IDataType" />.
        /// </summary>
        /// <param name="dataType">The <see cref="IDataType" /> instance.</param>
        /// <param name="editorControl">The <see cref="IDataType" /> editor control.</param>
        /// <returns>The control to validate.</returns>
        public override Control GetControlToValidate(T dataType, Control editorControl)
        {
            return base.GetControlToValidate(dataType, editorControl);
        }

        /// <summary>
        /// Method for performing special actions <b>before</b> creating the <see cref="IDataType" /> editor.
        /// </summary>
        /// <param name="dataType">The <see cref="IDataType" /> instance.</param>
        /// <param name="eventArgs">The <see cref="DataTypeLoadEventArgs"/> instance containing the event data.</param>
        /// <remarks>Called <b>before</b> the grid creates the editor controls for the specified <see cref="IDataType" />.</remarks>
        public override void Initialize(T dataType, DataTypeLoadEventArgs eventArgs)
        {
        }

        /// <summary>
        /// Method for performing special actions <b>after</b> the <see cref="IDataType" />
        /// <see cref="IDataEditor">editor</see> has been loaded.
        /// </summary>
        /// <param name="dataType">The <see cref="IDataType" /> instance.</param>
        /// <param name="eventArgs">The <see cref="DataTypeLoadEventArgs"/> instance containing the event data.</param>
        /// <remarks>Called <b>after</b> the grid creates the editor controls for the specified <see cref="IDataType" />.</remarks>
        public override void Configure(T dataType, DataTypeLoadEventArgs eventArgs)
        {
        }

        /// <summary>
        /// Method for executing special actions before saving the editor value to the database.
        /// </summary>
        /// <param name="dataType">The <see cref="T">datatype</see> instance.</param>
        /// <param name="eventArgs">The <see cref="DataTypeSaveEventArgs"/> instance containing the event data.</param>
        /// <remarks>Called when the grid is saved for the specified <see cref="T">datatype</see>.</remarks>
        public override void Save(T dataType, DataTypeSaveEventArgs eventArgs)
        {
            base.Save(dataType, eventArgs);
        }
    } 

Now, if you want to customize how the content picker value is displayed in the grid, create the following code in the `GetDisplayValue(T dataType)` method:

    if (dataType.Data.Value != null)
    {
        int id;

        if (int.TryParse(dataType.Data.Value.ToString(), out id))
        {
            var node = new Node(id);

            return string.Format("<a href='editContent.aspx?id={0}' title='Edit content'>Name: {1}<br/>Last updated: {2}</a>", node.Id, node.Name, node.UpdateDate);
        }

        return dataType.Data.Value.ToString();
    }

    return string.Empty;

Which will result in the grid rendering like this:

<img alt="Content Editor" src="../custom_datatype_handler_result.JPG" style="max-width:100%;"/>

##### Custom datatypes #####
Even though `DataType Grid` is compatible with [over 30 datatypes](/data-types/datatype-grid/compatible-datatypes), there is always room for improvement.
By overriding the `Initialize`, `Configure` and `Save` methods, it is possible to add compatibility with almost any datatype.  
Feel free to take a look at the [existing datatype handlers](https://ucomponents.codeplex.com/SourceControl/latest#uComponents.DataTypes/DataTypeGrid/Handlers/DataTypes/) to see how they tweak the datatype into being compatible with DTG.

##### List of known datatypes #####
<table class="table table-bordered table-striped">
  <thead>
    <tr>
        <th>Name</th>
        <th>DataType Class</th>
        <th>DataEditor Class</th>
    </tr>
  </thead>
  <tbody>
        <tr>
            <td>Label</td>
            <td><code>umbraco.editorControls.label.DataTypeNoEdit</code></td>
            <td><code>umbraco.editorControls.noEdit</code></td>
        </tr>
        <tr>
            <td>Numeric</td>
            <td><code>umbraco.editorControls.numberfield.IDataTypenteger</code></td>
            <td><code>umbraco.editorControls.numberField</code></td>
        </tr>
        <tr>
            <td>Simple Editor</td>
            <td><code>umbraco.editorControls.simpleEditor.simpleEditorDataType</code></td>
            <td><code>umbraco.editorControls.simpleEditor.SimpleEditor</code></td>
        </tr>
        <tr>
            <td>Textstring</td>
            <td><code>umbraco.editorControls.textfield.TextFieldDataType</code></td>
            <td><code>umbraco.editorControls.textfield.TextFieldEditor</code></td>
        </tr>
        <tr>
            <td>Media Picker</td>
            <td><code>umbraco.editorControls.mediapicker.MediaPickerDataType</code></td>
            <td><code>umbraco.editorControls.mediaChooser</code></td>
        </tr>
        <tr>
            <td>Dictionary Picker</td>
            <td><code>umbraco.editorControls.dictionaryPicker.dictionaryPickerDataType</code></td>
            <td><code>umbraco.editorControls.dictionaryPicker.dictionaryPicker</code></td>
        </tr>
        <tr>
            <td>Approved Color</td>
            <td><code>umbraco.editorControls.colorpicker.ColorPickerDataType</code></td>
            <td><code>umbraco.editorControls.colorPicker</code></td>
        </tr>
        <tr>
            <td>Checkbox list</td>
            <td><code>umbraco.editorControls.checkboxlist.checkboxListDataType</code></td>
            <td><code>umbraco.editorControls.checkboxlist.checkboxlistEditor</code></td>
        </tr>
        <tr>
            <td>Content Picker</td>
            <td><code>umbraco.editorControls.pagepicker.PagePickerDataType</code></td>
            <td><code>umbraco.editorControls.pagePicker</code></td>
        </tr>
        <tr>
            <td>Date Picker with time</td>
            <td><code>umbraco.editorControls.datefieldmultiple.DataTypeDatefieldMultiple</code></td>
            <td><code>umbraco.editorControls.dateField</code></td>
        </tr>
        <tr>
            <td>Date Picker</td>
            <td><code>umbraco.editorControls.datepicker.DateDataType</code></td>
            <td><code>umbraco.editorControls.dateField</code></td>
        </tr>
        <tr>
            <td>Dropdown multiple</td>
            <td><code>umbraco.editorControls.listbox.ListBoxDataType</code></td>
            <td><code>umbraco.editorControls.dropdownMultiple</code></td>
        </tr>
        <tr>
            <td>Folder Browser</td>
            <td><code>umbraco.editorControls.folderbrowser.DataTypeFolderBrowser</code></td>
            <td><code>umbraco.editorControls.folderBrowser</code></td>
        </tr>
        <tr>
            <td>Dropdown</td>
            <td><code>umbraco.editorControls.dropdownlist.DropdownListDataType</code></td>
            <td><code>umbraco.editorControls.dropdown</code></td>
        </tr>
        <tr>
            <td>Member Picker</td>
            <td><code>umbraco.editorControls.memberpicker.MemberPickerDataType</code></td>
            <td><code>umbraco.editorControls.memberPicker</code></td>
        </tr>
        <tr>
            <td>Radiobox</td>
            <td><code>umbraco.editorControls.radiobuttonlist.RadioButtonListDataType</code></td>
            <td><code>umbraco.editorControls.radiobox</code></td>
        </tr>
        <tr>
            <td>Related Links</td>
            <td><code>umbraco.editorControls.PickerRelations.PickerRelationsDataType</code></td>
            <td><code>umbraco.editorControls.PickerRelations.PickerRelationsPreValueEditor</code></td>
        </tr>
        <tr>
            <td>Richtext editor</td>
            <td><code>umbraco.editorControls.tinyMCE3.tinyMCE3dataType</code></td>
            <td><code>umbraco.editorControls.tinyMCE3.TinyMCE</code></td>
        </tr>
        <tr>
            <td>Tags</td>
            <td><code>umbraco.editorControls.tags.DataType</code></td>
            <td><code>umbraco.editorControls.tags.DataEditor</code></td>
        </tr>
        <tr>
            <td>Textbox multiple</td>
            <td><code>umbraco.editorControls.textfieldmultiple.textfieldMultipleDataType</code></td>
            <td><code>umbraco.editorControls.textfield.TextFieldEditor</code></td>
        </tr>
        <tr>
            <td>True/false</td>
            <td><code>umbraco.editorControls.yesno.YesNoDataType</code></td>
            <td><code>umbraco.editorControls.yesNo</code></td>
        </tr>
        <tr>
            <td>Ultimate Picker</td>
            <td><code>umbraco.editorControls.ultimatepicker.ultimatePickerDataType</code></td>
            <td><code>umbraco.editorControls.ultimatepicker.ultimatePickerDataEditor</code></td>
        </tr>
        <tr>
            <td>Upload</td>
            <td><code>umbraco.editorControls.uploadfield.DataTypeUploadField</code></td>
            <td><code>umbraco.editorControls.uploadField</code></td>
        </tr>
        <tr>
            <td>Image Cropper</td>
            <td><code>umbraco.editorControls.imagecropper.DataType</code></td>
            <td><code>umbraco.editorControls.imagecropper.DataEditor</code></td>
        </tr>
        <tr>
            <td>XPath CheckBoxList</td>
            <td><code>umbraco.editorControls.XPathCheckBoxList.XPathCheckBoxListDataType</code></td>
            <td><code>umbraco.editorControls.XPathCheckBoxList.XPathCheckBoxListDataEdit</code></td>
        </tr>
        <tr>
            <td>XPath DropDownList</td>
            <td><code>umbraco.editorControls.XPathDropDownList.XPathDropDownListDataType</code></td>
            <td><code>umbraco.editorControls.XPathDropDownList.XPathDropDownListDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/xpath-auto-complete/">uComponents: XPath Auto Complete</a></td>
            <td><code>uComponents.DataTypes.XPathAutoComplete.XPathAutoCompleteDataType</code></td>
            <td><code>uComponents.DataTypes.XPathAutoComplete.XPathAutoCompleteDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/character-limit/">uComponents: Character Limit</a></td>
            <td><code>uComponents.DataTypes.CharLimit.CharLimitDataType</code></td>
            <td><code>uComponents.DataTypes.CharLimit.CharLimitControl</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/check-box-tree/">uComponents: Checkbox Tree</a></td>
            <td><code>uComponents.DataTypes.CheckBoxTree.CheckBoxTreeDataType</code></td>
            <td><code>uComponents.DataTypes.CheckBoxTree.CheckBoxTreeDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/country-picker/">uComponents: Country Picker</a></td>
            <td><code>uComponents.DataTypes.CountryPicker.CountryPickerDataType</code></td>
            <td><code>uComponents.DataTypes.CountryPicker.CountryPickerDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/datatype-grid/">uComponents: DataType Grid</a></td>
            <td><code>uComponents.DataTypes.DataTypeGrid.DataType</code></td>
            <td><code>uComponents.DataTypes.DataTypeGrid.DataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/dropdown-checklist/">uComponents: Dropdown CheckList</a></td>
            <td><code>uComponents.DataTypes.DropdownCheckList.DDCList_DataType</code></td>
            <td><code>uComponents.DataTypes.DropdownCheckList.DDCList_DataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/elastic-textbox/">uComponents: Elastic TextBox</a></td>
            <td><code>uComponents.DataTypes.ElasticTextBox.ETB_DataType</code></td>
            <td><code>uComponents.DataTypes.ElasticTextBox.ETB_Control</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/enum-dropdownlist/">uComponents: Enum CheckBoxList</a></td>
            <td><code>uComponents.DataTypes.EnumCheckBoxList.EnumCheckBoxListDataType</code></td>
            <td><code>uComponents.DataTypes.EnumCheckBoxList.EnumCheckBoxListDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/enum-dropdownlist/">uComponents: Enum DropDownList</a></td>
            <td><code>uComponents.DataTypes.EnumDropDownList.EnumDropDownListDataType</code></td>
            <td><code>uComponents.DataTypes.EnumDropDownList.EnumDropDownListDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/file-dropdownlist/">uComponents: File DropDownList</a></td>
            <td><code>uComponents.DataTypes.FileDropDownList.FileDropDownListDataType</code></td>
            <td><code>uComponents.DataTypes.FileDropDownList.FileDropDownListControl</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/file-picker/">uComponents: FilePicker</a></td>
            <td><code>uComponents.DataTypes.FilePicker.FP_DataType</code></td>
            <td><code>uComponents.DataTypes.FilePicker.FP_Control</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/file-picker/">uComponents: ImagePoint</a></td>
            <td><code>uComponents.DataTypes.ImagePoint.ImagePointDataType</code></td>
            <td><code>uComponents.DataTypes.ImagePoint.ImagePointDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/incremental-textbox/">uComponents: Incremental TextBox</a></td>
            <td><code>uComponents.DataTypes.IncrementalTextBox.IT_DataType</code></td>
            <td><code>uComponents.DataTypes.IncrementalTextBox.IT_DataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/multiple-dates/">uComponents: Multiple Dates</a></td>
            <td><code>uComponents.DataTypes.MultipleDates.MD_DataType</code></td>
            <td><code>uComponents.DataTypes.MultipleDates.MD_DataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/multi-url-picker/">uComponents: Multi-URL Picker</a></td>
            <td><code>uComponents.DataTypes.MultiUrlPicker.MultiUrlPickerDataType</code></td>
            <td><code>uComponents.DataTypes.MultiUrlPicker.MultiUrlPickerDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/notes/">uComponents: Notes</a></td>
            <td><code>uComponents.DataTypes.Notes.NotesDataType</code></td>
            <td><code>uComponents.DataTypes.Notes.NotesDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/property-picker/">uComponents: Property Picker</a></td>
            <td><code>uComponents.DataTypes.PropertyPicker.PropertyPickerDataType</code></td>
            <td><code>uComponents.DataTypes.PropertyPicker.PropertyPickerDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/relation-links/">uComponents: Relation Links</a></td>
            <td><code>uComponents.DataTypes.RelationLinks.RelationLinksDataType</code></td>
            <td><code>uComponents.DataTypes.RelationLinks.RelationLinksDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/render-macro/">uComponents: Render Macro</a></td>
            <td><code>uComponents.DataTypes.RenderMacro.RenderMacroDataType</code></td>
            <td><code>uComponents.DataTypes.RenderMacro.RenderMacroDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/similarity/">uComponents: Similarity</a></td>
            <td><code>uComponents.DataTypes.Similarity.SimilarityDataType</code></td>
            <td><code>uComponents.DataTypes.Similarity.SimilarityDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/sql-auto-complete/">uComponents: SQL AutoComplete</a></td>
            <td><code>uComponents.DataTypes.SqlAutoComplete.SqlAutoCompleteDataType</code></td>
            <td><code>uComponents.DataTypes.SqlAutoComplete.SqlAutoCompleteDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/sql-checkboxlist/">uComponents: SQL CheckBoxList</a></td>
            <td><code>uComponents.DataTypes.SqlCheckBoxList.SqlCheckBoxListDataType</code></td>
            <td><code>uComponents.DataTypes.SqlCheckBoxList.SqlCheckBoxListDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/sql-dropdownlist/">uComponents: SQL DropDownList</a></td>
            <td><code>uComponents.DataTypes.SqlDropDownList.SqlDropDownListDataType</code></td>
            <td><code>uComponents.DataTypes.SqlDropDownList.SqlDropDownListDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/sub-tabs/">uComponents: Sub Tabs</a></td>
            <td><code>uComponents.DataTypes.SubTabs.SubTabsDataType</code></td>
            <td><code>uComponents.DataTypes.SubTabs.SubTabsDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/textstring-array/">uComponents: Textstring Array</a></td>
            <td><code>uComponents.DataTypes.TextstringArray.TextstringArrayDataType</code></td>
            <td><code>uComponents.DataTypes.TextstringArray.TextstringArrayControl</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/toggle-box/">uComponents: ToggleBox</a></td>
            <td><code>uComponents.DataTypes.ToggleBox.TB_DataType</code></td>
            <td><code>uComponents.DataTypes.ToggleBox.TB_Control</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/url-picker/">uComponents: URL Picker</a></td>
            <td><code>uComponents.DataTypes.UrlPicker.UrlPickerDataType</code></td>
            <td><code>uComponents.DataTypes.UrlPicker.UrlPickerDataEditor</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/user-picker/">uComponents: User Picker</a></td>
            <td><code>uComponents.DataTypes.UserPicker.UserPickerDataType</code></td>
            <td><code>uComponents.DataTypes.UserPicker.UserPickerControl</code></td>
        </tr>
        <tr>
        	<td><a href="http://ucomponents.org/data-types/xml-dropdownlist/">uComponents: XML Dropdown List</a></td>
        	<td><code>uComponents.DataTypes.XmlDropDownList.XmlDropDownListDataType</code></td>
        	<td><code>System.Web.UI.WebControls.DropDownList</code></td>
        </tr>
        <tr>
            <td><a href="http://ucomponents.org/data-types/xpath-auto-complete/">uComponents: XPath AutoComplete</a></td>
            <td><code>uComponents.DataTypes.XPathAutoComplete.XPathAutoCompleteDataType</code></td>
            <td><code>uComponents.DataTypes.XPathAutoComplete.XPathAutoCompleteDataEditor</code></td>
        </tr>
    </tbody>
</table>