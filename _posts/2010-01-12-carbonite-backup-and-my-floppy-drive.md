---
id: 144
title: Carbonite backup and my floppy drive
date: 2010-01-12T21:52:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=144
permalink: /2010/01/carbonite-backup-and-my-floppy-drive.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2010/01/carbonite-backup-and-my-floppy-drive.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/2281848851572773081
image: /wp-content/uploads/2010/01/Carbonite1-672x372.png
categories:
  - backup
  - carbonite
  - floppy
  - Windows
---
Recently I switched to Carbonite on two machines at home.  After installing the software and starting the backup, I noticed that frequently something would be accessing the floppy drive (or at least trying). Googling around a little bit revealed that this was one of Carbonite's "features".

The two suggestions that kept coming up during my search were:

  * Insert a floppy, and Carbonite will learn that that drive is a floppy drive  
    - Sorry, that didn't work
  * Disconnect the floppy drive  
    - Wait, and then open case when the drive needs to be used? Bad idea!!

  There is a third option: disable the floppy drive in Windows.

  If you open My Computer, you'll see something similar to this:

![Carbonite floppy](/wp-content/uploads/2010/01/Carbonite1.png)

  Notice the 3 1/2 Floppy - that's the one making all the noise. But not for long!

  Right-click on the icon, and select Properties from the drop-down menu. Click on the Hardware tab and select the Floppy disk drive.

![Carbonite floppy properties](/wp-content/uploads/2010/01/Carbonite2.png)

  Click on the Properties button.

![Carbonite floppy do not use](/wp-content/uploads/2010/01/Carbonite3.png)

  On the bottom of the screen is a drop-down box. Click on the drop-down arrow and change the selection to "Do not use this device (disable)". Click OK.

![Carbonite floppy no A-drive](/wp-content/uploads/2010/01/Carbonite4.png)

Click OK on the screen with the 3 1/2 inch Floppy properties, and return to the My Computer screen. Your Floppy Drive A: should be gone, and with it the seeking Carbonite tries to do on it!