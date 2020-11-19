---
id: 133
title: iTunes 9.1 authorization and Windows 7
date: 2010-06-23T11:47:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=133
permalink: /2010/06/itunes-9-1-authorization-and-windows-7.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2010/06/itunes-91-authorization-and-windows-7.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/6166101589783128086
categories:
  - 64-bit
  - Administrator
  - DRM
  - itunes
  - Music
  - rights
  - UAC
  - Windows
  - windows 7
---
I recently started working with Windows 7 on my work computer (expect a slew of updates to the old Vista postings 🙂 ) and ran into some problems with iTunes. First off, it needed the special 64-bit installer to be run (I'm using Windows 7 64-bit), even though after doing that it installed almost everything in _C:Program Files (x86)_ (the default directory for 32-bit applications).

Then I tried to sync to my iPod. Oops, I forgot to authorize the new computer. So I authorized it. All seemed well, except for the Audible audiobooks... I added the Audible manager, authorized the Audible account in iTunes, and resynchronized. Now it came up with the message _Some of the items in the iTunes library, including "...", were not copied to the iPod "..." because you are not authorized for them on this computer._ Yes I am. I just authorized them. Doing the authorization again confirmed that. I even restored my iPod to factory default settings (and forgot that to complete that you have to plug it in to a wall socket... 🙁 ). None of that helped - I still got the message.

That same message (or similar at least) popped up when I tried to play one of the protected files. And no matter how often I authorized the computer, and iTunes kept telling me that it is already authorized, it didn't want to stick. Now, since Vista, Microsoft has introduced this new security model, mainly consisting of User Access Control (UAC), but also a change in what is considered an Administrator. In XP, it was sufficient to be part of the local administrator's group. Under Windows 7 (and Vista), there is a distinct difference between running as a user of the Administrator's group, and the option _Run as Administrator_. And apparently iTunes needs that!

After setting iTunes to Run as Administrator, I started it up and tried to play one of the protected songs. iTunes told me the computer wasn't authorized, so I authorized it (again...). This time it seemed to stick however! The song actually played. And now it seems to actually synchronize all the songs, including the protected ones.

It does seem to take excruciatingly longer to synchronize when running iTunes as Administrator. Also, it makes me feel a little uncomfortable to say the least: it shouldn't run as Administrator constantly. But it solved the issue for now, and I hope anyone else out there can benefit from this.. 🙂