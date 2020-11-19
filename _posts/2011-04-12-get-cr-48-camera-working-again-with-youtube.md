---
id: 67
title: Get Cr-48 camera working again with YouTube
date: 2011-04-12T08:00:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=67
permalink: /2011/04/get-cr-48-camera-working-again-with-youtube.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2011/04/get-cr-48-camera-working-again-with.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/4124613366321636448
image: /wp-content/uploads/2011/04/cr48-1.jpg
categories:
  - cr48
  - google
  - Network
  - webcam
  - youtube
---
![](/wp-content/uploads/2011/04/cr48-1.jpg)

I played around with the Cr-48 camera a few weeks ago, and noticed that you can easily upload video to YouTube. Today I noticed it was broken - YouTube said that no camera was detected.

Luckily the fix was only a Google search away. It turns out that on the about:plugins page there are two Flash players shown. Disable the one that has version number 10.2.158.6, path /opt/google/chrome/pepper/libpepflashplayer.so. Reopen the YouTube upload page, and all should be well.

(Thanks to <a href="https://groups.google.com/group/cr-48-test-pilots/browse_thread/thread/18566f0b3e22632c?fwc=1" target="_blank">Google Groups, Cr-48 Test Pilots</a>)