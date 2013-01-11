---
layout: extension
title: IO
category: XSLT Extensions
since_version: 2.0
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.IO" alias="ucomponents.io" />
		...
	</XsltExtensions>

*****

## Methods
Here are available methods in the ```IO``` library:

* [DirectoryExists](#directoryexists)
* [FileExists](#fileexists)
* [GetDirectories](#getdirectories)
* [GetFiles](#getfiles)
* [GetExtension](#getextension)
* [GetFileName](#getfilename)
* [GetFileNameWithoutExtension](#getfilenamewithoutextension)
* [GetDirectoryName](#getdirectoryname)
* [GetFileSize](#getfilesize)
* [GetServerMapPath](#getservermappath)
* [MapPath](#mappath)
* [PathShortener](#pathshortener)
* [FormatFileSize](#formatfilesize)
* [LoadFile](#loadfile)
* [GetFileInfo](#getfileinfo)
* [GetLocalFilePath](#getlocalfilepath)

*****

### DirectoryExists
Directories the exists.
_Returns_: Returns true if the directory exists, otherwise false.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:DirectoryExists(path)" />


*****

### FileExists
Files the exists.
_Returns_: Returns true if the file exists, otherwise false.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:FileExists(path)" />


*****

### GetDirectories
Gets the directories.
_Returns_: Returns a node-set of the directories.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |
| searchPattern | ```System.String``` | |
| allDirectories | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:GetDirectories(path, searchPattern, allDirectories)" />


*****

### GetFiles
Gets the files.
_Returns_: Returns a node-set of the files.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |
| searchPattern | ```System.String``` | |
| allDirectories | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:GetFiles(path, searchPattern, allDirectories)" />


*****

### GetExtension
Gets the extension.
_Returns_: Returns the extension of the specified path string.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:GetExtension(path)" />


*****

### GetFileName
Gets the name of the file.
_Returns_: Returns the file name and extension of the specified path string.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:GetFileName(path)" />


*****

### GetFileNameWithoutExtension
Gets the file name without extension.
_Returns_: Returns the file name of the specified path string without the extension.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:GetFileNameWithoutExtension(path)" />


*****

### GetDirectoryName
Gets the name of the directory.
_Returns_: Returns the directory name for the specified path string.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:GetDirectoryName(path)" />


*****

### GetFileSize
Gets the size of the file.
_Returns_: Returns the filesize for the specified filepath.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:GetFileSize(path)" />


*****

### GetServerMapPath
Gets the mapped path to the server.
_Returns_: Returns the physical file path that corresponds to the specified virtual path on the web server.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:GetServerMapPath(path)" />


*****

### MapPath
Gets the mapped path to the server.
_Returns_: Returns the physical file path that corresponds to the specified virtual path on the web server.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |
| useHttpContext | ```System.Boolean``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:MapPath(path, useHttpContext)" />


*****

### PathShortener
Truncates the middle section of a string, this is ideal for long filepaths or URLs.
_Returns_: Returns a shortened path of the string.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| input | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:PathShortener(input)" />


*****

### FormatFileSize
Formats the size of the file.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| filesize | ```System.Int64``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:FormatFileSize(filesize)" />


*****

### LoadFile
Loads and reads the contents of a file.
_Returns_: Returns the contents of the specified file.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| filepath | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:LoadFile(filepath)" />


*****

### GetFileInfo
Gets the FileInfo.
_Returns_: Returns the System.IO.FileInfo for the specified filepath.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:GetFileInfo(path)" />


*****

### GetLocalFilePath
Checks if the file path is a Uri, then returns the local file path.
_Returns_: Returns the local file path.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| path | ```System.String``` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.io:GetLocalFilePath(path)" />


*****

