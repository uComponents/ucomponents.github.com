---
layout: datatype
title: DataType Grid
category: Data Types
description: DataType Grid is basically a DataType that allows you to store DataTypes in a grid-like fashion. Think Excel, but with other Datatypes instead of textboxes.
since_version: 3.0
---

### Table of contents ###
* [Prevalue Editor](../#prevalue_editor)
* [Content Editor](../#content_editor)
* [Compatible Datatypes](../compatible-datatypes)
* **Localization**    
    - [Content Editor](#content_editor)    
    - [Prevalue Editor](#prevalue_editor)    
* [Razor Samples](../razor-samples)
* [Integration](../integration)
    
    
## Localization ##
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