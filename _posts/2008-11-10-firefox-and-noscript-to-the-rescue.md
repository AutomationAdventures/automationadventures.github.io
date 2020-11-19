---
id: 190
title: Firefox and NoScript to the rescue
date: 2008-11-10T13:54:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=190
permalink: /2008/11/firefox-and-noscript-to-the-rescue.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2008/11/firefox-and-noscript-to-rescue.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/4290521362926730503
categories:
  - clickjacking
  - cross-site
  - csrf
  - firefox
  - javascript
  - Miscellaneous
  - noscript
  - Security
  - security now
---
I've been an avid listener of the <a href="http://www.grc.com/securitynow.htm" target="_blank">Security Now</a> podcast for a couple of years now, and learned a lot of interesting things concerning cryptography, possible avenues of attack on your home network, etc. But two recent episodes of SN showed me that the Internet is a dark and dangerous place, and that you need all the protection you can get. In this case, <a href="http://www.firefox.com/" target="_blank">Firefox </a>with the <a href="http://noscript.net/" target="_blank">NoScript</a> plug-in.

Before the two episodes aired, Steve Gibson had stressed the danger of having JavaScript executing in your browser when visiting an unknown site. This was my first encounter with NoScript, which, as the name implies, prevents Javascript from executing. The advantage above just turning off Javascript all together, is that you can allow certain sites, and block certain others. It can be a hassle sometimes to figure out which site you need to turn on to allow your webpage to display properly, but the added security is IMHO worth it.

The first episode that peeked my interest was episode 166, "<a href="http://www.grc.com/sn/sn-166.htm" target="_blank">Cross-Site Request Forgery</a>". Steve does a much better job in explaining this, but in a nutshell it is the technique that one site uses your cookies for another site to issue a GET request on a form, by displaying an "image". Much to my surprise, NoScript was mentioned as a plugin for Firefox to prevent this.

The second episode was even more sinister. Episode 168, "<a href="http://www.grc.com/sn/sn-168.htm" target="_blank">ClickJacking</a>", describes how a page can use an Iframe to display another page behind innocent looking content, and trick you into clicking on a button in the hidden page instead of on the displayed page. This can be used to activate your camera and microphone in Flash, or change your password on MySpace to something only the owner of the malicious website knows. Once again, NoScript was suggested as the way to prevent this from happening to you.

So, Firefox with NoScript comes to the rescue of the beleagured Internet user. And I'm impressed with the development done on NoScript: starting out as a "simple" tool to turn JavaScript on and off for sites, it has now grown into the armor that is added to Firefox to protect you from most malicious websites.

Unless, of course, you turn off the script protection, as both Steve Gibson and Leo LaPorte confessed to in the <a href="http://www.grc.com/sn/sn-169.htm" target="_blank">latest</a> Q&A episode.... 🙂