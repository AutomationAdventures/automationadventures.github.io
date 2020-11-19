---
id: 180
title: Cursor keys not working in Ubuntu 8.10 VMWare client
date: 2009-02-10T12:59:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=180
permalink: /2009/02/cursor-keys-not-working-in-ubuntu-8-10-vmware-client.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/02/cursor-keys-not-working-in-ubuntu-810.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/8209542114521003276
categories:
  - "8.10"
  - client
  - cursor keys
  - intrepid
  - keyboard
  - Linux
  - ubuntu
  - vmware
---
After last week's problem with the Terminal Services client, I also experienced problems with the cursor keys in the VMWare client for Ubuntu 8.10. This was particularly annoying, since I use Quicken in a VMWare machine, and the selection of categories is much easier with the cursor keys than with the mouse.

It turns out that this is <a href="https://bugs.launchpad.net/ubuntu/+bug/289098" target="_blank">a bug in Ubuntu Intrepid 8.10</a>. None of the patches since October 2008 have addressed this issue, but the manual fix is very simple:

  * Open a terminal window
  * Type the following in the terminal:  
    > echo 'xkeymap.nokeycodeMap = true' > ~/.vmware/config 

After entering this you have to restart your VMWare client session. If it doesn't work, try restarting the VMWare server, however, since this is a client setting, it shouldn't affect the server or be affected by server settings.