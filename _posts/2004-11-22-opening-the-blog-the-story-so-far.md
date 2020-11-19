---
id: 391
title: 'Opening the blog - the story so far'
date: 2004-11-22T16:14:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=391
permalink: /2004/11/opening-the-blog-the-story-so-far.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2004/11/opening-blog-story-so-far_22.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/937953939794577802
categories:
  - Linux
  - X10
---
Well, after some deliberation I decided to keep a log (more precise a blog) of the adventures in X10 automation. This log is started after I've been fiddling around with X10 automation for a while, so in brief the setup that I have:

  * [CM-11A controller](http://www.smarthome.com/1142.html)
  * 4 Lamp modules (2 [X10](http://www.smarthome.com/2000.html)'s and 2 [LampLinc PLC](http://www.smarthome.com/2000S.html)'s)
  * 2 Appliance modules (both [ApplianceLinc PLC](http://www.smarthome.com/2002S.html)'s)
  * 1 X10 [Maxi controller](http://www.smarthome.com/4020.html)
  * 1 X10 RF receiver

The two appliance modules haven't been installed yet, because when I tried to install them, it looked like we had a problem with the two phases in our home, and some trouble with weak signal. When using Smarthome's trouble-shooting guide, the advise was to install a [repeater-coupler.](http://www.smarthome.com/4826a.html) After installing this the systems seems to work more reliable (one of the lamp modules would react only every now and then to signals it seemed, but reacts to them every time since installing the repeater-coupler), but I haven't had a chance yet to readdress the issue with the ApplianceLinc's.

As controlling software I use [MisterHouse](http://www.misterhouse.net/). It's running on an old Pentium PC, with barely enough memory etc. to support the web interface. But it's enough to run Linux and MisterHouse, and it's running a whole lot more stable than the Windows version that was on there.

I'll try and keep an account of my adventures into X10 in this blog. Home automation can be fun, but also very frustrating at times...