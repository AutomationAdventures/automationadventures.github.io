---
id: 28
title: How to disable WPS on the Netgear N600 router
date: 2012-02-01T08:00:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=28
permalink: /2012/02/how-to-disable-wps-on-the-netgear-n600-router.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2012/02/how-to-disable-wps-on-netgear-n600.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/268741879516067831
image: /wp-content/uploads/2012/02/Netgear_WPS_1.png
categories:
  - netgear
  - Network
  - Security
  - setup
  - wps
---
Recently a [vulnerability](http://en.wikipedia.org/wiki/Wi-Fi_Protected_Setup#Security_issues) in the [WPS wireless network setup](http://en.wikipedia.org/wiki/Wi-Fi_Protected_Setup) was discovered. I will not go into great detail on that vulnerability here, but will simply show you how to turn this off on the Netgear N600:

  1. Start the Netgear maintenance tool by going to [http://www.routerlogin.net](http://www.routerlogin.net/). This takes you into the setup tool installed during initial setup.
  2. Locate the Advanced Wireless settings
  ![](/wp-content/uploads/2012/02/Netgear_WPS_1.png)
  3. Make sure the check box next to "WPS disabled" is checked.
  ![](/wp-content/uploads/2012/02/Netgear_WPS_2.jpg)

Normally the "WPS disabled" option is checked when the router detects an intrusion attempt, and you can clear it here. In this case, we do the opposite - we disable the WPS by telling the router it is getting hacked.