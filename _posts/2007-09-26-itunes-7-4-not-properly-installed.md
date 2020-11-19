---
id: 270
title: iTunes 7.4 not properly installed
date: 2007-09-26T14:52:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=270
permalink: /2007/09/itunes-7-4-not-properly-installed.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/09/itunes-74-not-properly-installed.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/7772559840516034491
categories:
  - 64-bit
  - apple
  - drivers
  - GEAR
  - installation
  - itunes
  - Music
  - vista
  - Windows
---
Somewhere along the upgrade trail from 7.3 to 7.4.2, I started getting the annoying message "iTunes was not properly installed. If you wish to import or burn CDs, you need to reinstall iTunes" whenever I start iTunes. After following this advice, and restarting iTunes, I got the message "iTunes was not properly installed. If..." - OK, you got the idea...

Apparently a [lot](http://forums.guru3d.com/showthread.php?p=2419844) of [other](http://discussions.apple.com/thread.jspa?messageID=5375736) people [seem](http://forums.macnn.com/82/applications/347378/itunes-7-4-out/) to [be](http://www.somelifeblog.com/2007/09/apple-itunes-7412-problems-warning.html) having this problem. And it happens under Vista 32 and 64 bit. Despite the message, people are reporting that importing works fine (I haven't seen any messages confirming that burning a CD still works).

A [discussion thread](http://discussions.apple.com/thread.jspa?messageID=5375736) on the Apple Support forum helped me out: simply installing the [GEAR Software drivers](http://gearsoftware.com/support/drivers.cfm) seemed to resolve at least the message. In some cases, a new error message pops up saying it can't find the folder with the CD settings. In that case you have to uninstall iTunes 7.4.x, install 7.3.2, copy the CD folder to a safe location, uninstall iTunes 7.3.2, reinstall iTunes 7.4.x, install the GEAR driver, and copy the CD folder back.

I haven't tried importing or burning a CD yet, but at least iTunes starts without pausing for me to click OK!