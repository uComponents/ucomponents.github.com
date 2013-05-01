---
layout: extension
title: Dates
category: XSLT Extensions
since_version: 2.0
---

## Activation

### Version 6.0.0 (and above)
As of uComponents v6.0.0 all XSLT extensions are automatically registered with Umbraco. Newly created XSLT files (in the back-office) will already contain the appropriate namespaces.  For existing XSLT files, you will still need to add the `ucomponents.dates` namespace.

### Prior to version 6.0.0

Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Dates" alias="ucomponents.dates" />
		...
	</XsltExtensions>

*****

## Methods
Here are available methods in the `Dates` library:

* [AddWorkdays](#addworkdays)
* [Age](#age)
* [DateWithinDuration](#datewithinduration)
* [DateWithinLastDays](#datewithinlastdays)
* [ElapsedSeconds](#elapsedseconds)
* [FormatDateTime](#formatdatetime)
* [GetFirstDayOfMonth](#getfirstdayofmonth)
* [GetLastDayOfMonth](#getlastdayofmonth)
* [GetPrettyDate](#getprettydate)
* [IsLeapYear](#isleapyear)
* [IsWeekday](#isweekday)
* [IsWeekend](#isweekend)
* [ListDates](#listdates)
* [ParseExact](#parseexact)
* [ToUnixTime](#tounixtime)
* [WorkdaysDiff](#workdaysdiff)

*****

### AddWorkdays
Adds the workdays, excluding weekends.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| date | `System.String` | |
| days | `System.Int32` | |
| format | `System.String` | _(optional - defaults to `dd MMMM yyyy`)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:AddWorkdays(umbraco.library:CurrentDate(), 7, 'dd/MM/yyyy')" />

*****

### Age
Get the current age, from the specified date of birth.<br/>
_Returns_: Returns the age based on the specified date of birth.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| dateOfBirth | `System.String` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:Age('1978-07-30')" />

*****

### DateWithinDuration
Tests if a date is within the specified duration.<br/>
_Returns_: Returns true or false depending on if the date is within the specified duration.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| date | `System.String` | |
| duration | `System.String` | The duration in [XSD Duration format](http://msdn.microsoft.com/en-us/library/ms256220.aspx). |

#### XSLT Example

	<!-- if the content node was created within the last 7 days, then do ... -->
	<xsl:if test="ucomponents.dates:DateWithinDuration($currentPage/@createDate, '7D')">
		...
	</xsl:if>

*****

### DateWithinLastDays
Tests if a date is within the last number of specified days.<br/>
_Returns_: Returns true or false depending on if the date is within the last number of days.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| date | `System.String` | |
| days | `System.Int32` | |

#### XSLT Example

	<!-- if the content node was created within the last 7 days, then do ... -->
	<xsl:if test="ucomponents.dates:DateWithinLastDays($currentPage/@createDate, 7)">
		...
	</xsl:if>

*****

### ElapsedSeconds
Gets the elapsed seconds since the input `DateTime`.<br/>
_Returns_: Returns the elapsed seconds since the input `DateTime`.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| input | `System.String` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:ElapsedSeconds($currentPage/@createDate)" />

*****

### FormatDateTime
Converts the value of the date time string to its equivalent string representation using the specified format.<br/>
_Returns_: The formatted date string

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| date | `System.String` | |
| format | `System.String` | _(note - the use of `S` returns the day-number suffix)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:FormatDateTime($currentPage/@createDate, 'ddd ddS MMMM yyyy')" />

*****

### GetFirstDayOfMonth
Gets the first day of month.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| date | `System.String` | |
| format | `System.String` | _(optional - defaults to `dd MMMM yyyy`)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:GetFirstDayOfMonth(umbraco.library:CurrentDate(), 'dd/MM/yyyy')" />

*****

### GetLastDayOfMonth
Gets the last day of month.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| date | `System.String` | |
| format | `System.String` | _(optional - defaults to `dd MMMM yyyy`)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:GetLastDayOfMonth(umbraco.library:CurrentDate(), 'dd/MM/yyyy')" />

*****

### GetPrettyDate
Gets the pretty date.<br/>
_Returns_: Returns a pretty date.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| date | `System.String` | |
| format | `System.String` | _(optional - defaults to `dd MMMM yyyy`)_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:GetPrettyDate($currentPage/@createDate, 'dd MMMM yyyy')" />

*****

### IsLeapYear
Determines whether [is leap year] [the specified date].<br/>
_Returns_: true if [is leap year] [the specified date]; otherwise, false.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| date | `System.String` | |

#### XSLT Example

	<xsl:if test="ucomponents.dates:IsLeapYear(umbraco.library:CurrentDate())">
		<blink>Hurray! It's a leap year!</blink>
	</xsl:if>

*****

### IsWeekday
Determines whether the specified date is weekday.<br/>
_Returns_: true if the specified date is weekday; otherwise, false.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| date | `System.String` | |

#### XSLT Example

	<xsl:choose>
		<xsl:when test="ucomponents.dates:IsWeekday(umbraco.library:CurrentDate())">
			<span class="sad-panda">Boo! It's a weekday!</span>
		</xsl:when>
		<xsl:otherwise>
			<blink>Hurray! It's the weekend!</blink>
		</xsl:otherwise>
	</xsl:choose>

*****

### IsWeekend
Determines whether the specified date is weekend.<br/>
Internally this is the opposite of the [IsWeekday](#isweekday) method.<br/>
_Returns_: true if the specified date is weekend; otherwise, false.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| date | `System.String` | |

#### XSLT Example

	<xsl:choose>
		<xsl:when test="ucomponents.dates:IsWeekend(umbraco.library:CurrentDate())">
			<blink>Hurray! It's the weekend!</blink>
		</xsl:when>
		<xsl:otherwise>
			<span class="sad-panda">Boo! It's a weekday!</span>
		</xsl:otherwise>
	</xsl:choose>

*****

### ListDates
Lists all the dates between the start and end dates.<br/>
Internally this method uses `umbraco.library.Split` to separate the dates into a list.<br/>
_Returns_: Returns a nodeset of all the dates between the start and end date.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| startDate | `System.String` | |
| endDate | `System.String` | |

#### XSLT Example

	<ul>
		<xsl:for-each select="ucomponents.dates:ListDates('2013-06-12', '2013-06-14')/value">
			<li>
				<xsl:value-of select="text()" />
			</li>
		</xsl:for-each>
	</ul>

*****

### ParseExact
Parses the exact value of the date time string to its equivalent string representation using the specified format.<br/>
_Returns_: Returns a sortable date/time formatted to the specified pattern.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| date | `System.String` | |
| inputFormat | `System.String` | |
| outputFormat | `System.String` | _(optional - defaults to `"s"` "[Sortable date/time pattern](http://msdn.microsoft.com/en-us/library/az4se3k1.aspx)")_ |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:ParseExact('12-31-2012', 'MM-dd-yyyy', 'dd-MM-yyyy')" />

*****

### ToUnixTime
Converts a date to Unix time.<br/>
_Returns_: Return the total number of seconds between Unix epoch and the specified date/time.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| date | `System.String` | |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:ToUnixTime($currentPage/@createDate)" />

*****

### WorkdaysDiff
Gets the number of workdays between two dates.<br/>
_Returns_: Returns the number of workdays between two dates.

#### Parameters
| Name | Type | Notes |
|------|------|-------|
| startDate | `System.String` | |
| endDate | `System.String` | |

#### XSLT Example

	<!-- get the number of workdays (excludes weekends) from when the node was created -->
	<xsl:value-of select="ucomponents.dates:WorkdaysDiff($currentPage/@createDate, umbraco.library:CurrentDate())" />

*****
