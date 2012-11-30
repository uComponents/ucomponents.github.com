---
layout: extension
title: Dates
category: XSLT Extensions
---

## Activation
Enabling the XSLT extension for use in your XSLT templates.
Add the following XML snippet to your `~/config/xsltExtensions.config` file:

	<XsltExtensions>
		...
		<ext assembly="uComponents.XsltExtensions" type="uComponents.XsltExtensions.Dates" alias="ucomponents.dates" />
		...
	</XsltExtensions>

## Methods
Here are available methods:

### DateWithinLastDays
Tests if a date is within the last number of specified days.
_Returns_: Returns true or false depending on if the date is within the last number of days.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |
| days | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:DateWithinLastDays(date, days)" />


*****

### DateWithinDuration
Tests if a date is within the specified duration.
_Returns_: Returns true or false depending on if the date is within the specified duration.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |
| duration | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:DateWithinDuration(date, duration)" />


*****

### GetPrettyDate
Gets the pretty date.
_Returns_: Returns a pretty date.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:GetPrettyDate(date)" />


*****

### GetPrettyDate
Gets the pretty date.
_Returns_: Returns a pretty date.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |
| format | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:GetPrettyDate(date, format)" />


*****

### FormatDateTime
Converts the value of the date time string to its equivalent string representation using the specified format.
_Returns_: The formated date string

#### Parameters
| Name | Type |
|------|------|
| date | System.String |
| format | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:FormatDateTime(date, format)" />


*****

### ParseExact
Parses the exact value of the date time string to its equivalent string representation using the specified format.
_Returns_: Returns a sortable date/time formatted to the specified pattern.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |
| inputFormat | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:ParseExact(date, inputFormat)" />


*****

### ParseExact
Parses the exact value of the date time string to its equivalent string representation using the specified format.
_Returns_: Returns a sortable date/time formatted to the specified pattern.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |
| inputFormat | System.String |
| outputFormat | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:ParseExact(date, inputFormat, outputFormat)" />


*****

### ElapsedSeconds
Gets the elapsed seconds since the input DateTime.
_Returns_: Returns the elapsed seconds since the input DateTime.

#### Parameters
| Name | Type |
|------|------|
| input | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:ElapsedSeconds(input)" />


*****

### Age
Get the current age, from the specified date of birth.
_Returns_: Returns the age based on the specified date of birth.

#### Parameters
| Name | Type |
|------|------|
| dateOfBirth | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:Age(dateOfBirth)" />


*****

### IsLeapYear
Determines whether [is leap year] [the specified date].
_Returns_: true if [is leap year] [the specified date]; otherwise, false.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:IsLeapYear(date)" />


*****

### IsWeekday
Determines whether the specified date is weekday.
_Returns_: true if the specified date is weekday; otherwise, false.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:IsWeekday(date)" />


*****

### IsWeekend
Determines whether the specified date is weekend.
_Returns_: true if the specified date is weekend; otherwise, false.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:IsWeekend(date)" />


*****

### AddWorkdays
Adds the workdays, excluding weekends.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |
| days | System.Int32 |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:AddWorkdays(date, days)" />


*****

### AddWorkdays
Adds the workdays, excluding weekends.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |
| days | System.Int32 |
| format | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:AddWorkdays(date, days, format)" />


*****

### GetFirstDayOfMonth
Gets the first day of month.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:GetFirstDayOfMonth(date)" />


*****

### GetFirstDayOfMonth
Gets the first day of month.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |
| format | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:GetFirstDayOfMonth(date, format)" />


*****

### GetLastDayOfMonth
Gets the last day of month.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:GetLastDayOfMonth(date)" />


*****

### GetLastDayOfMonth
Gets the last day of month.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |
| format | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:GetLastDayOfMonth(date, format)" />


*****

### ListDates
Lists all the dates between the start and end dates.
_Returns_: Returns a nodeset of all the dates between the start and end date.

#### Parameters
| Name | Type |
|------|------|
| startDate | System.String |
| endDate | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:ListDates(startDate, endDate)" />


*****

### ToUnixTime
Converts a date to Unix time.
_Returns_: Return the total number of seconds between Unix epoch and the specified date/time.

#### Parameters
| Name | Type |
|------|------|
| date | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:ToUnixTime(date)" />


*****

### WorkdaysDiff
Gets the number of workdays between two dates.
_Returns_: Returns the number of workdays between two dates.

#### Parameters
| Name | Type |
|------|------|
| startDate | System.String |
| endDate | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:WorkdaysDiff(startDate, endDate)" />


*****

### FormatDateTime
Formats the date time.

#### Parameters
| Name | Type |
|------|------|
| date | System.DateTime |
| format | System.String |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:FormatDateTime(date, format)" />


*****

### GetDayNumberSuffix
Gets the ordinal suffix for a given date
_Returns_: The ordinal suffix

#### Parameters
| Name | Type |
|------|------|
| date | System.DateTime |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:GetDayNumberSuffix(date)" />


*****

### IsWeekday
Determines whether the specified day is weekday.
_Returns_: true if the specified day is weekday; otherwise, false.

#### Parameters
| Name | Type |
|------|------|
| day | System.DayOfWeek |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:IsWeekday(day)" />


*****

### WorkdaysDiff
Gets the number of workdays between two dates.
_Returns_: Returns the number of workdays between two dates.

#### Parameters
| Name | Type |
|------|------|
| startDate | System.DateTime |
| endDate | System.DateTime |

#### XSLT Example

	<xsl:value-of select="ucomponents.dates:WorkdaysDiff(startDate, endDate)" />


*****

