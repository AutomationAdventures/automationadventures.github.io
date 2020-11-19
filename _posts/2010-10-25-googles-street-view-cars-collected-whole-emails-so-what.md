---
id: 115
title: 'Google''s Street View cars collected whole emails - so what?'
date: 2010-10-25T07:00:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=115
permalink: /2010/10/googles-street-view-cars-collected-whole-emails-so-what.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2010/10/google-street-view-cars-collected-whole.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/7682594160802384928
image: /wp-content/uploads/2010/10/Subway-camera-567x372.jpg
categories:
  - encryption
  - Features
  - google
  - Lifestyle
  - privacy
  - streetview
---
In May of this year Google [announced](http://googleblog.blogspot.com/2010/05/wifi-data-collection-update.html) that their Street View cars, who also collected WiFi data to assist in positioning your smart phone etc., had captured some of the unencrypted data that was received. In that announcement they stated that they only received fragments of data. Last week, they [announced](http://googleblog.blogspot.com/2010/10/creating-stronger-privacy-controls.html) that in some cases whole emails were captured.

Of course, their official reaction has to be "we're very sorry, we shouldn't have done this, and we'll get rid of it immediately." But remember what they captured - unencrypted data, being broadcast by people who probably didn't even know they did it. In fact, I think Google did them a service, by pointing out that their "private" data was being broadcast in the clear in a radius of about a city block. And apart from that, think of the data that an ISP sees and can capture (or allow to be captured), even if you use encrypted WiFi: all the data that Google has captured, emails, URLS, etc. and then some.


![We still watching you! - junicks](/wp-content/uploads/2010/10/Subway-camera.jpg)

It seems to me the same knee-jerk reaction that happens with Street View pictures, especially in Germany. Although all the information Google collects with Street View is publicly available for anyone at the same position, it suddenly becomes a major issue when Google collects it. Oh, and the "opt out" where Germans can tell Google not to show their house in detail on Street View - another knee-jerk. Have all these people removed their address from the phone book, so they can't be identified in that way? Did they smudge their license plates, so no one can trace them that way?

So, how can you prevent Google Street View from capturing your data? Two ways:

  * Enable encryption on your WiFi network
  * Use a secure web protocol to communicate with the network

Enabling encryption on your WiFi network has to be done on all devices. Your router determines the level of encryption, and all devices connecting through WiFi have to support that encryption level. Don't use WEP, but opt for WPA2 without TKIP (AES only).

Using a secure web protocol is simply using https where possible. Sites like Google Mail support this, and even Google Search <a href="http://www.google.com/support/websearch/bin/answer.py?answer=173733&hl=en" target="_blank">can be run over https</a>.

I'm not a Google Fanboy, although I use several Google products daily. But this seems like singling out Google for things that are common occurrences, or for things that can be easily prevented.