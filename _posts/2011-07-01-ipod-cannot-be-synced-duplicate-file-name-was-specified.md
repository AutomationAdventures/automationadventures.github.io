---
id: 42
title: 'iPod cannot be synced - Duplicate file name was specified'
date: 2011-07-01T07:00:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=42
permalink: /2011/07/ipod-cannot-be-synced-duplicate-file-name-was-specified.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2011/07/ipod-cannot-be-synced-duplicate-file.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/1899508922059282496
image: /wp-content/uploads/2011/07/HD_Repair-434x372.jpg
categories:
  - error
  - Features
  - fix
  - ipod
  - Music
  - sync
---
After about 5 years, I'm in the process of replacing my 3rd generation iPod with a 30GB hard disk with a brand new 4th generation iPod Touch with 32GB of SD. While I'm still holding on to the old iPod, I'm switching back and forth on syncing the iPod and the iPod Touch. Until I got an error on the old iPod that it cannot be synced, because there was a duplicate file name.

The solution is actually very simple. Somehow the file system on the iPod is corrupt, and you'll have to rebuild it. On Windows, this can be done in two ways:

  1. If you plug the iPod in, a screen comes up automatically suggesting you scan and fix this device. Check both boxes to make sure a complete scan is complete.
  2. If that screen doesn't pop up, click on Start, My Computer. Windows then shows you all the storage devices connected to your computer. Right-click on the iPod, and select Properties. In the screen that pop ups, select the Tools tab. On that tab, select the Check Now button in Error Checking.
  ![](/wp-content/uploads/2011/07/HD_Repair.jpg)
    
It may take a long time to scan, but it should finish. When it finishes, unplug the iPod, wait 1 minute, then plug it back in. It should work now. If it doesn't, open up iTunes, select the iPod in the Devices section, and select Restore. After the restore finishes, do the Error Check on the iPod one more time.