---
id: 181
title: Cursor keys not working in Ubuntu Terminal Services client
date: 2009-01-26T12:23:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=181
permalink: /2009/01/cursor-keys-not-working-in-ubuntu-terminal-services-client.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/01/cursor-keys-not-working-in-ubuntu.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/3441205476364093100
categories:
  - cursor
  - en-us
  - keyboard
  - keys
  - Linux
  - Network
  - remote desktop
  - terminal services
  - ubuntu
  - us
  - Windows
---
I'm using VPN and the Terminal Services client pretty frequently to access my computer at work. As discussed in <a href="/2009/01/07/ubuntu-810-connect-to-cisco-vpn-through-vpnc/" target="_blank">this article</a>, the Ubuntu VPN setup is much simpler in 8.10. However, when using the Terminal Services client, I had some problems with some of the function keys, in particular the cursor keys.

Now, being an old Unix hack, I managed to use the hjkl keys to navigate around the vi screen, but in some of the applications, this became an issue. With some Googling, the solution turned out to be fairly simple.

When you start up the Terminal Services client, go to the Local Resources tab. Under the keyboard heading, select as your keyboard language en-us instead of us. Now connect to the remote computer, and all the keys should function as they were intended.

Hope this helps somebody!