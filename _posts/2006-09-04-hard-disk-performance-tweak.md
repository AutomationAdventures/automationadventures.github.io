---
id: 325
title: Hard disk performance tweak
date: 2006-09-04T08:40:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=325
permalink: /2006/09/hard-disk-performance-tweak.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2006/09/hard-disk-performance-tweak_04.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/891484881616370759
categories:
  - Windows
---
Don't tell your wife that with Labor Day weekend, you'll have plenty of time. She'll cheerfully make sure you don't... 🙂

It's not as bad as it sounds here: we were talking about the weekend, and my dear wife mentioned that if I had some time, could I take a look at why her computer was so slow. Sure!

I first checked for the usual suspects, spyware, adware etc. <a href="http://www.google.com/url?sa=t&ct=res&cd=1&url=http%3A%2F%2Fwww.safer-networking.org%2F&ei=Ih_8RKC6EqHOwQLyvq33DQ&sig=__x33d7wOfJewJbKPUhDu-x_nADH0=&sig2=puhii6YyjEF6-2hdI1f6CQ" target="_blank">Spybot S&D</a> is up to version 1.4 now, and <a href="http://www.lavasoftusa.com/software/adaware/" target="_blank">AdAware</a> is still going strong. Neither one found anything. Then I checked the hard disk space. The disk was about 80% used, which prompted me to do a disk clean up. That helped a bit, but not much. Maybe defrag? Why not? (Well, because it takes forever, that's why not).

No success. Then I remembered reading an article about the hard disk controller being stuck in PIO mode, even though I'm pretty sure her computer has Ultra-DMA (it seems to have found a controller for it). A quick check, and sure enough, the primary IDE channel had switched to PIO modem. Some digging (haha) around found <a href="http://neodon.blogspot.com/2006/07/little-known-tweak-to-boost-hard-drive.html" target="_blank">the article by James Barton</a>. It describes a step-by-step on how to fix this problem, and prevent it from happening again. Just because blogs sometimes disappear, I've copied the steps below:

  1. Open up the Registry Editor.
  2. Navigate to the following key: HKEY\_LOCAL\_MACHINESYSTEMCurrentControlSetControlClass{4D36E96A-E325-11CE-BFC1-08002BE10318}.
  3. There are several sub-keys under this one, such as 0000, 0001, etc. You are interested in two of them that say Primary IDE Channel and Secondary IDE Channel.
  4. Make the following changes to both of those keys:
  1. Delete any attributes named MasterIdDataCheckSum or SlaveIdDataCheckSum. This resets the tracking for errors that Windows uses to determine when the transfer mode should be lowered.
  2. Add an attribute with the name ResetErrorCountersOnSuccess and a DWORD value of 1. This tells Windows that it should lower the transfer mode when there are six consecutive  
    errors instead of six cumulative errors.
  3. If they exist, set the following keys to a hexadecimal value of ffffffff (eight F's). This  
    will change the transfer modes to UltraDMA-6:
  * MasterDeviceTimingMode
  * MasterDeviceTimingModeAllowed
  * SlaveDeviceTimingMode
  * SlaveDeviceTimingModeAllowed
  * UserMasterDeviceTimingModeAllowed
  * UserSlaveDeviceTimingModeAllowed

  4. Reboot your computer and check the devices to see if they are set to UltraDMA Mode 6.

Reading through some of the comments, you need to check the BIOS to make sure it's setup to support DMA for the hard disks (another article states that Dell is known to turn this off - guess what, my wife has a Dell...), and it is prudent to make a backup before mucking around with these settings.

So I guess I'll be making a backup today, and see if there's anything I can do about that DMA mode...

**Update:** I just finished backing up and modifying the parameters, and her machine sure is a whole lot snappier. As a test I ran iTunes playing her music library, and starting up both Firefox and Thunderbird. The sound didn't hiccup once. Thanks James!