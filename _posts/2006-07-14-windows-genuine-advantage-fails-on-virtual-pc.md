---
id: 343
title: Windows Genuine Advantage fails on Virtual PC
date: 2006-07-14T16:08:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=343
permalink: /2006/07/windows-genuine-advantage-fails-on-virtual-pc.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2006/07/windows-genuine-advantage-fails-on_14.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/8803118515984744601
categories:
  - Windows
---
Wow. That sucked.  
Today I ran across an announcement that [Microsoft Virtual PC](http://www.microsoft.com/windows/virtualpc/default.mspx) was available for free. Since I need to install a new release of some software, and didn't want to risk my main machine, I thought Virtual PC would be nice. And it is. Right up until you want to run Windows Updates.  
After going through some updates for the checker, the Windows update decided it was time to validate my Windows installation with Windows Genuine Advantage. Which failed miserably. Several times. With an error code 0x80242006.  
Before you accuse me of piracy, this is an Enterprise copy, installed on all our machines at work (and as you can tell by the posting time, I'm at work...). This morning one of the admins used that same copy to install and update a regular machine. So it must be something with the VirtualPC.  
It turns out I'm not the only one: a quick google for 0x80242006 resulted in about 86 hits. The top one ([www.mydigitallife.info](http://www.mydigitallife.info/2006/06/08/windows-update-kb905474-and-kb913446-installation-failed-with-error-code-0x80242006/)) immediately sent me to the right site to download the [Windows Genuine Advantage update](http://www.download.windowsupdate.com/msdownload/update/v3-19990518/cabpool/windowsxp-kb905474-enu-x86_4bafa8793e8cdcaf4ba4ffc494df32d496154544.exe) directly. Yeah, I know this link is to an executable. It seems to be safe though.  
After installing this update, all seems well. I'm actually continuing the installation now, and dreading the upgrade from SP1 to SP2 in a Virtual PC...