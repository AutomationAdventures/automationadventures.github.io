---
id: 329
title: Setting up VPN on Ubuntu 6.06 LTS
date: 2006-08-29T22:32:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=329
permalink: /2006/08/setting-up-vpn-on-ubuntu-6-06-lts.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2006/08/setting-up-vpn-on-ubuntu-606-lts_29.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/9069035981574391305
categories:
  - Linux
  - Network
  - Windows
---
Slowly but surely I'm getting to a [working Ubuntu workstation](/2006/08/desktop-switch-to-ubuntu.html). Tonight I finally made some time to set up the VPN connection - thereby freeing myself from lugging a Windows laptop to and from work every day...

Instrumental in setting this up were two websites: [PattonCentral](http://www.pattoncentral.org/?p=30) (describing his experiences on setting up version 4.6 and 4.8 of the Cisco VPN Client), and [popey.com](http://popey.com/node/62), which is the actual step-by-step instructions (although they are for version 4.6 - version 4.8 doesn't need the patching as described).

After that, starting the VPN client was simple, and by using the built-in Terminal Server Client I was able to access my work desktop computer. For the connection protocol: RDP works, but RDPv5 works better if you're using lots of Windows keys.

Next step - bloody iPod synchronization (still haven't quite figured out gtkPod...).