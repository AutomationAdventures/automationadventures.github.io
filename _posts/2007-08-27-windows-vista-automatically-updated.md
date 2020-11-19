---
id: 277
title: Windows Vista automatically updated
date: 2007-08-27T13:31:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=277
permalink: /2007/08/windows-vista-automatically-updated.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/08/windows-vista-automatically-updated.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/4589649175084511629
categories:
  - Security
  - Windows
---
This morning when I got to the computer at work, it was a little sluggish. Not thinking anything of it, I decided to restart the machine - it's running Vista 64-bit, and for some reason there are some problems with Microsoft's Most Secure Windows Ever.

However, during the shutdown, I saw the message "Configuring Updates" come by. And sure enough, during the startup, Windows happily announced that it was "Installing Updates".

Wait a minute. I know it was a long weekend, but I sure as hell didn't install any updates that required a reboot... So what happened?

Well, apparently, "Download updates but let me choose whether to install them" doesn't mean what I thought it meant. And according to [Slated](http://slated.org/)';s [blog post](http://slated.org/windows_by_stealth_the_updates_you_dont_want), I'm not the only one.

When checking the update log, it shows an update to the Windows Update program. Most likely this is related to the Windows Genuine Advantage problem from last week, but what good is telling the OS that you want things done a certain way, when it then happily turns around and does something else?

I think they call that a bug. Some other people call it malware. I for one feel less and less in control of a machine that is sitting on my desk, and that I use to write software for our company...!