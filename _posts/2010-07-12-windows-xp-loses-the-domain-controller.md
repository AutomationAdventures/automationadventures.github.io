---
id: 130
title: Windows XP loses the domain controller?
date: 2010-07-12T16:15:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=130
permalink: /2010/07/windows-xp-loses-the-domain-controller.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2010/07/windows-xp-loses-domain-controller.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/867614728307262876
categories:
  - domain
  - logon
  - vmware
  - Windows
---
I ran into an interesting problem last week with some Virtual Machines. I've set up 3 different machines, each running Windows XP with a different version of Progress (10.0, 10.1, and 10.2), to test how our application works under the various Progress versions and to develop with some of the latest tools (I love the Eclipse interface! 🙂 ). However, for some reason last week all the virtual machines, plus the virgin Windows XP install, decided to show me the following error message:

> Windows cannot connect to the domain, either because the domain controller is down or otherwise unavailable, or because your computer account was not found.

Since I was rolling out a change to a web service running under 10.1 at the time, I was not a happy camper. It took me the better part of a day to try and come up with a solution. Unfortunately, none surfaced, even after some helpful hints from our systems engineer ("Did you reboot?" - "Yes." - "Must be a Windows patch." - "I have had no new patches in the last week and half." etc.). The weekend came and went, and today I was back at the same problem. Ruling out anything general (like the domain controller actually being down - we could log in to everything except the VMs), I started scouring the Internets. And lo and behold, back in 2006 <a href="http://www.mydigitallife.info/2006/10/09/unable-to-logon-to-win2003-domain-ad-due-to-windows-cannot-connect-to-the-domain-error/" target="_blank">someone else</a> had the same problem. With a regular XP machine. In a Windows domain. Wow!

In a nutshell, it comes down to the fact that the domain controller is confused about your machine and SID, and won't trust you. Removing the machine from the domain, and adding it back in, solves the problem somehow.

Thank you, <a href="http://www.mydigitallife.info/" target="_blank">My Digital Life</a>!