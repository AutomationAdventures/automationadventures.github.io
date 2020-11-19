---
id: 19
title: Macro for Pivot table dates
date: 2013-02-11T18:12:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=19
permalink: /2013/02/macro-for-pivot-table-dates.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2013/02/macro-for-pivot-table-dates.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/2311636413836127043
image: /wp-content/uploads/2013/02/Excel_256x.png
categories:
  - analysis services
  - excel
  - visual basic
---
![](/wp-content/uploads/2013/02/Excel_256x.png)

I have a small Excel workbook with two Pivot tables, linking each to their own Analysis Services cube. The purpose of these two pivot tables is to daily compare the bookings and shipments data. This involves making a change to the date filter, making sure that both pivot tables use the same date, and formatting the tables to the content.

I finally broke down, and dove into the macro editor in Excel. Since I had no idea how the macro editor works, I decided to record the actions. When I pulled the editor, this is what I saw:  
<a name='more'></a>

<pre>Sub Macro1()<br />'<br />' Macro1 Macro<br />'<br /><br />'<br />    ActiveSheet.PivotTables("PivotTable1").PivotFields( _<br />        "[Calendar Filter].[Calendar Year - Quarter - Month - Date].[Calendar Year]"). _<br />        ClearAllFilters<br />    ActiveSheet.PivotTables("PivotTable1").PivotFields( _<br />        "[Calendar Filter].[Calendar Year - Quarter - Month - Date].[Calendar Year]"). _<br />        CurrentPageName = _<br />        "[Calendar Filter].[Calendar Year - Quarter - Month - Date].[Calendar Year].&[2013].&[1].&[01].&[2013-01-03T00:00:00]"<br />    ActiveSheet.PivotTables("PivotTable2").PivotFields( _<br />        "[Transaction Date].[Calendar Year Qtr Month].[Calendar Year]").ClearAllFilters<br />    ActiveSheet.PivotTables("PivotTable2").PivotFields( _<br />        "[Transaction Date].[Calendar Year Qtr Month].[Calendar Year]"). _<br />        CurrentPageName = _<br />        "[Transaction Date].[Calendar Year Qtr Month].[Date].&[20130103]"<br /><br />End Sub<br /></pre>

The important parts are the reference to the date filters in the cube. These will become driven by a variable containing a date. However, the trick is to change the date into strings, and specifically parts of the date into strings. We need the year, quarter, month, and actual date in two different formats. I used two different functions to accomplish this.

  * DatePart can take a part of the date, specified by the first parameter.
  * Format changes between different data types, like integer to character.

So, to replace the hard coded quarter 4 with the quarter of the date variable, you would use Format(DatePart("q",vtDate),"d"). Using these functions, and a few others, I wound up with the following code:

<pre>Sub ChangeDate()<br />'<br />' ChangeDate Macro<br />' Update the date in both date boxes to same date (yesterday)<br />'<br />' Keyboard Shortcut: Ctrl+d<br />'<br />    Dim vcDateName As String<br />    Dim vcDateYear As String<br />    Dim vcDateQuarter As String<br />    Dim vcDateMonth As String<br />    Dim vcDateTime As String<br />    <br />    Dim vtTheDate As Date<br />    <br />' Get Yesterday's date<br />    vtTheDate = Date - 1<br />    <br />' Format the various necessary fields<br />    vcDateName = Format(vtTheDate, "yyyymmdd")<br />    vcDateYear = Format(vtTheDate, "yyyy")<br />    vcDateMonth = Format(vtTheDate, "m")<br />    vcDateQuarter = Format(DatePart("q", vtTheDate) + 1, "d")<br />    vcDateTime = Format(vtTheDate, "yyyy-mm-dd")<br />        <br />    ActiveSheet.PivotTables("PivotTable1").PivotFields( _<br />        "[Calendar Filter].[Calendar Year - Quarter - Month - Date].[Calendar Year]"). _<br />        ClearAllFilters<br />    ActiveSheet.PivotTables("PivotTable1").PivotFields( _<br />        "[Calendar Filter].[Calendar Year - Quarter - Month - Date].[Calendar Year]"). _<br />        CurrentPageName = _<br />        "[Calendar Filter].[Calendar Year - Quarter - Month - Date].[Calendar Year].&[" + vcDateYear + "].&[" + vcDateQuarter + "].&[" + vcDateMonth + "].&[" + vcDateTime + "T00:00:00]"<br />    ActiveSheet.PivotTables("PivotTable2").PivotFields( _<br />        "[Transaction Date].[Calendar Year Qtr Month].[Calendar Year]").ClearAllFilters<br />    ActiveSheet.PivotTables("PivotTable2").PivotFields( _<br />        "[Transaction Date].[Calendar Year Qtr Month].[Calendar Year]"). _<br />        CurrentPageName = _<br />        "[Transaction Date].[Calendar Year Qtr Month].[Date].&[" + vcDateName + "]"<br />    Cells.Select<br />    Selection.Columns.AutoFit<br />End Sub<br /></pre>

Link this macro to a keyboard shortcut and instead of editing two date fields manually, we now only have to use the shortcut to retrieve the newest data.