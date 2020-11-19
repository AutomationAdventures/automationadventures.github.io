---
id: 388
title: A new router in the home
date: 2005-01-11T01:02:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=388
permalink: /2005/01/a-new-router-in-the-home.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2005/01/new-router-in-home_10.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/1149381012672291914
categories:
  - Network
---
I've installed a new router over the weekend.

Some time ago I was thinking about the setup of our home network. I bought a Linksys [BEFSR41](http://www.linksys.com/products/product.asp?grid=34&scid=29&prid=561) Cable/DSL Router years ago when we first signed up for Internet over the cable. Then when we moved to our new home, and we'd have computers upstairs and downstairs, I added a Linksys [WAP54G](http://www.linksys.com/products/product.asp?grid=33&scid=35&prid=608). Now downstairs we have a PC with a wireless card, and a TiVo with a wireless USB adapter. Adding the XBox would mean another wireless adapter, and when we want to add a TiVo in the master bedroom would mean yet another wireless adapter. Time to rethink this.

It occurred to me that with three devices downstairs that wanted to be added to the home network, they could all share one wireless connection. So my idea was to use the existing WAP54G as an uplink to the new wireless broadband router [WRT54G](http://www.linksys.com/products/product.asp?grid=33&scid=35&prid=601), and the BEFSR41 as a hub for the three devices. That would only require buying the WRT54G.

The first step was completed this weekend: I transferred all connections and settings from the BEFSR41/WAP54G duo over to the WRT54G. All went well, except for one little hiccup: it is advised to beef up security on your wireless devices. One of the small steps you can take is not broadcasting your SSID (the name of the network). However, even after I specified the name in all the devices, they wouldn't connect. The solution proved to be frighteningly simple: broadcast the SSID, let your devices connect, then turn of the SSID broadcasting. Apparently somehow the network devices "remember" the SSID after seeing it...

The next step will be trying to let the WAP54G talk to the WRT54G somehow. But that will be a project for another weekend.