---
id: 113
title: 'Google Refine 2.0 - a tool for working with messy data'
date: 2010-11-16T07:00:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=113
permalink: /2010/11/google-refine-2-0-a-tool-for-working-with-messy-data.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2010/11/google-refine-20-tool-for-working-with.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/297918889123062478
image: /wp-content/uploads/2010/11/Google-Refine-logo.png
categories:
  - database
  - etl
  - freebase
  - google
  - open source
  - Software
---
![Google Refine logo](/wp-content/uploads/2010/11/Google-Refine-logo.png)

I recently came across a tool called <a href="http://code.google.com/p/google-refine/" target="_blank">Google Refine</a>. This tool (formerly known as Freebase Gridworks) can take large amounts of data, and analyze the contents of different colums. Recently <a href="http://google-refine.blogspot.com/2010/11/google-refine-20.html" target="_blank">Google released Refine 2.0</a>, and added extension architecture, a reconciliation framework and lots of new transformation commands and expressions.

With Google Refine you can import, analyze, transform and export raw data. It's basically an ETL tool, but with a lot of features that are only available in commercial ETL tools.

The example video below shows how a set of contracts are analyzed, and how the different spellings and representations of "Firm Fixed Price" and "Time and Materials" are cleaned up and combined - comparable to the "refining" of raw materials.

[![Google Refine 2.0](http://img.youtube.com/vi/yNccGtn3Wb0/0.jpg)](http://www.youtube.com/watch?v=yNccGtn3Wb0)

The most awesome feature I've seen so far is the possibility to make a change to your raw data, and undo everything all the way up to the original import of the data. Considering the amount of data that can be manipulated with Google Refine, that's pretty impressive!

Refine 2.0 can import data in the following formats:

  * TSV, CSV or values separated by a custom separator you specify
  * Excel (both .xls and .xlsx)
  * XML, RDF as XML
  * JSON
  * Google Spreadsheets

and it can export your results as:

  * TSV
  * CSV
  * Excel
  * HTML table
  * User defined formats, by using a Template Exporter. There's a default of JSON and a tutorial on exporting it as YAML.

There is also an option to link your Refine data to other data sources, currently limited to web services supporting the <a href="http://code.google.com/p/google-refine/wiki/ReconciliationServiceApi" target="_blank">Reconciliation Service API</a>.

Google Refine is open source, and does not run on one of the Google servers, but locally inside your network. So any sensitive data will not leave your network!