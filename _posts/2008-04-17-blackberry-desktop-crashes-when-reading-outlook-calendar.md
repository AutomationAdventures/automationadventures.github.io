---
id: 233
title: Blackberry Desktop crashes when reading Outlook calendar
date: 2008-04-17T10:14:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=233
permalink: /2008/04/blackberry-desktop-crashes-when-reading-outlook-calendar.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2008/04/blackberry-desktop-crashes-when-reading.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/298489913653539384
categories:
  - blackberry
  - crash
  - desktop
  - Productivity
  - synchronization
  - Telecom
  - vista
  - Windows
---
For the past two days, my Blackberry Desktop software has crashed when it was trying to read the Outlook calendar entries. Rebooting didn't help, and I really didn't want to reinstall software and go through the pain of resynchronizing.

Luckily, the solutions was relatively simple. After Googling around for a bit, I came across [this post](http://www.blackberryforums.com/rim-software/36729-ms-outlook-synchronization-error.html#post885771) on [BlackberryForums.com](http://www.blackberryforums.com/), describing an easy and effective way to make my Blackberry's calendar match my Outlook calendar (again).

The KB entry referenced (KB 11703 on the [BlackBerry Technical Solution Center](http://www.blackberry.com/btsc)) describes the procedure for Windows 2000/XP. The procedure is similar on Windows Vista, the only difference is that the Intellisync folder is located at _C:Users&lt;user name&gt;AppDataRoamingResearch In MotionBlackBerryIntellisync_. You don't even have to reconfigure the synchronization settings - after deleting the Intellisync directory, start the Desktop Manager and synchronize your Blackberry.

But I have to agree with the post directly below the solution: I wonder what got it messed up to begin with...