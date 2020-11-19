---
id: 318
title: Banshee Music Player for Ubuntu
date: 2006-12-30T20:23:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=318
permalink: /2006/12/banshee-music-player-for-ubuntu.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2006/12/banshee-music-player-for-ubuntu_30.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/1311752311295886559
categories:
  - Linux
  - Music
---
Another missing piece in the list of applications that I found essential seems to have been resolved: [Banshee Music Player](http://banshee-project.org/Main_Page) is replaced iTunes.

The version that is included with the standard Ubuntu 6.06 LTS is version 0.10, and although pretty good, I desperately missed the podcast support. Using iPodder to get the podcasts and import them into Banshee was a short-term solution - I don't like doing repetative tasks by hand... 🙂

On the Banshee website was mention of version 0.11.3, which came out earlier this month, with support for Podcasts..! Since I had a little bit of trouble trying to install some of the plug-ins (missing libraries and utilities), I was a little wary to install 0.11.3 from scratch, until I found [this excellent How-To](http://linuxrevolution.blogspot.com/2006/12/howto-banshee-0113-on-ubuntu.html) on getting all the prerequisites, the source code itself, and all compilation/installation instructions!

It takes a while to get through them all (depending on how many libraries you already have installed), and I had two hiccups (#1 was during Step 1, I had to use libsgutil1 and libsgutils1-dev with Ubuntu 6.06 instead of libsgutils and libsgutils-dev, #2 was during the configuration of ipod-sharp - I needed to install the mono-gac package).

I just fired it up, and seems to work OK! I just added 6 feeds to the podcast module, and I'll update the episodes a little later. For now, great stuff, and thansk to the folks at Banshee for creating the cool application, and GameGod of [Linux Revolution](http://linuxrevolution.blogspot.com/index.html) for the great How To!