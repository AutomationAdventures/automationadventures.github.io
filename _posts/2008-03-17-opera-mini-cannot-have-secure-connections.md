---
id: 242
title: Opera Mini cannot have secure connections
date: 2008-03-17T14:20:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=242
permalink: /2008/03/opera-mini-cannot-have-secure-connections.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2008/03/opera-mini-cannot-have-secure.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/4630649003284764713
categories:
  - blackberry
  - opera mini
  - pearl
  - Telecom
---
I got a new cellphone a couple of weeks ago, and in trying to follow where several men have gone before, I got a [BlackBerry](http://www.blackberry.com/) ([Pearl 8130](http://na.blackberry.com/eng/devices/series-detail.jsp?navId=H0,C101) to be precise).

One of the things that really appealed to me was the possibility to surf the net from pretty much anywhere that Verizon Wireless has coverage. But the built-in browser was a little clunky, and I had heard about [Opera](http://www.opera.com/) for cellphones. I was able to install [Opera Mini](http://www.operamini.com/) without much problems, and liked some of the extra features it had over the standard BlackBerry browser.

Right until I listened to episode 126 of the [Security Now!](http://www.grc.com/securitynow.htm) podcast. In that episode Leo reads an email from a listener (Anand K.), describing that he discovered how the Opera Mini browser talks to the Internet. It doesn't talk directly to web servers, it talks to a transcoder server, which is like a proxy with extras. The use of this transcoder server makes it impossible to provide end-to-end SSL security for client connections. The [show notes](http://www.grc.com/sn/SN-126.htm) for episode 126 do a pretty good explanation on how this affects the possibility of having secure connections, and how the Opera Mini transcoder has to have access to all your data, your passwords, user name, login, cookies, etc.etc. Not only that, but all the information is then transmitted in the clear to the actual web server...

To be fair, Opera describes this behavior in their [FAQ](http://www.operamini.com/help/faq/#security), but this is terrible! If you use your mobile phone for anything that requires security, ditch Opera Mini immediately. Opera suggests to install Opera Mobile, however, I don't think there is a version for the BlackBerry. Back to the built-in browser...