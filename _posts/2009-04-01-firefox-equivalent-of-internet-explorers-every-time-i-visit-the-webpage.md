---
id: 170
title: 'Firefox equivalent of Internet Explorer''s Every Time I visit the Webpage'
date: 2009-04-01T11:06:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=170
permalink: /2009/04/firefox-equivalent-of-internet-explorers-every-time-i-visit-the-webpage.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/04/firefox-equivalent-of-internet-explorer.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/2486480906897959994
categories:
  - cache
  - firefox
  - IE
  - Linux
  - Macintosh
  - Windows
  - XML
---
We have a little rotating web page setup in our break room, and have been using a dial indicator to show our performance in bookings and shipments. However, due to the nature of the set-up (a page, showing a flash file, that is configured by an XML file), it turned out to be necessary in Internet Explorer to use the option "Every time I visit the webpage" on the "Check for newer versions of stored pages:" setting in the Temporary Internet Files and History Settings.

Unfortunately, Internet Explorer 7 still can't handle CSS properly, so some of the tables looked horrible. Switching to Firefox fixed that problem. But now the old data was showing. And where is that "Newer versions of stored pages" setting in Firefox???

It's hiding in the config. In the address bar, type

> about:config

Then find the setting **browser.cache.check\_doc\_frequency**, and change it to **1**. This will duplicate the Internet Explorer behavior (as far as loading cached page goes, mind you!).

The options for this setting are as follows:

| Value | Description |
| 0 | Check for a new version of a page once per session |
| 1 | Check for a new version every time a page is loaded |
| 2 | Never check for a new version - always load the page from cache |
| 3 | Check for a new version when the page is out of date (Default) |

