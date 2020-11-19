---
id: 272
title: Vista network performance while playing music
date: 2007-09-18T14:50:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=272
permalink: /2007/09/vista-network-performance-while-playing-music.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/09/vista-network-performance-while-playing.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/4493398163860075421
categories:
  - DRM
  - itunes
  - Music
  - Network
  - performance
  - vista
  - Windows
---
Yeah, I just got bit by that Vista "feature"... the one where your network slows down when you play music. That one, yeah.

I just added an index to our database, unfortunately from the client side. While I was chastising myself for doing it client-server instead of host-based, I was watching the number of records being updated per second. Hmm, about 400... maybe if I shutdown some programs. First, Sidebar - it displays some RSS feeds and weather information. OK, up to 420-440 records/sec. Not bad...

Then I remembered reading something about the Vista network stack and playing music files. I closed iTunes, and lo and behold: I now was updating about 1800 records/sec! Over 4 times as much??? Me thinks Vista has a problem there. This is on a dual-core 2.4GHz Intel with 2GB RAM.

[ZDNet](http://zdnet.com/) has an article with [Microsoft's response to the Vista network performance issue](http://blogs.zdnet.com/hardware/?p=724), and while some of the arguments may be true (only local network operations, two high priority drivers contending for the same resource, etc.), I still think it's funny that a dual processor system would have its network performance so drastically reduced.

Anyone thinks it's the DRM...? Anyone...?