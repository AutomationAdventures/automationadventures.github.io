---
id: 159
title: Outlook shows some appointments off by 1 hour
date: 2009-10-21T16:12:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=159
permalink: /2009/10/outlook-shows-some-appointments-off-by-1-hour.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/10/outlook-shows-some-appointments-off-by.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/7184668393684752032
categories:
  - appointment
  - DST
  - microsoft
  - outlook
  - Productivity
  - Windows
---
Well, it's that time of the year again, Daylight Savings is about to end, and Outlook decides that some of my recurring appointments now happen 1 hour later.

Mind you, not all of them. I still have lunch appointments at 12PM, but I now have a recurring alarm to go home at 6PM instead of 5PM. That sounds like my boss is getting me to work an extra hour, but fortunately the recurring appointment "Commute to work" is starting at 8:30AM instead of 7:30AM...

Oh, and my Blackberry synchronizes with Outlook, but somehow manages to correct the braindead appointments to their correct time.

This seems to happen pretty much twice every year, ever since the US government decided to extend DST by a couple of weeks. We've patched all our servers and clients, ran conversion tools left and right, but it still happens. Creating a new appointment doesn't really fix the problem - I have to wait until next week to make that appointment, and by mid-November they'll be off again!

Luckily some Googling brought me to <a href="http://help.wugnet.com/office/Outlook-Recurring-Meetings-hour-extended-DST-ftopict1076063.html" target="_blank">this </a>post, and although it mainly discusses problems with Exchange and the Blackberry Enterprise Server, it does contain a reference to a Microsoft tool for Outlook (<a href="http://support.microsoft.com/kb/931667/" target="_blank">KB931667</a>). To my surprise this tool was updated in August 2008 (hasn't it been a couple of years since the change in DST?). After installing and running the tool, it found 13 appointments to fix. When I gave it the go-ahead and fix these culprits, the problem magically disappeared!

My only fear now is that I have to run this again on November 2nd... we'll see.