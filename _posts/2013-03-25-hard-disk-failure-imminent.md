---
id: 18
title: Hard disk failure imminent!
date: 2013-03-25T12:00:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=18
permalink: /2013/03/hard-disk-failure-imminent.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2013/03/hard-disk-failure-imminent.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/2443145481653396875
image: /wp-content/uploads/2013/03/7800750212_6e9813544c.jpg
categories:
  - backup
  - harddisk
  - Linux
  - tuxboot
---
![](/wp-content/uploads/2013/03/7800750212_6e9813544c.jpg)

A couple of weeks Windows 7 informed me that my hard disk is failing, and that I should back up immediately. Skeptical of Windows messages about things like this, I decided to run [Spinrite](http://www.grc.com/sr/spinrite.htm) on the disk. After making a backup with [Carbonite](http://www.carbonite.com/).

Apparently I should have not done that. The better course of action would have been to copy the whole hard disk to a new one, and _then_ run Spinrite on the old disk.

By doing this, I apparently pushed the disk just enough so it ran out of spare sectors for relocating bad tracks. I found this out after I got a new 1TB disk, placed it in the same computer, and tried to copy the old disk to the new disk.  

Copying the disk turned out to be an adventure as well. At first I tried to do it the old fashioned way: boot in Linux, and run a dd from the old disk to the new disk. This works great on working disks, but failing disks disrupt the dd command...

Finally I ran across [CloneZilla](http://clonezilla.org/) and [tuxboot](http://www.tuxboot.org/). Tuxboot is actually a great utility that lets you turn a CloneZilla Live, DRBL Live, GParted Live or Tux2live installation into a bootable USB or DVD disk, without too much thought. CloneZilla is the open source equivalent of Norton Ghost.

After downloading tuxboot and selecting the CloneZilla Live installation, the download quickly completed and I now had a USB stick to boot from. Taking it back to the PC with the failing hard drive, reboot, and voila, CloneZilla.

CloneZilla has a lot of options, and there are great step-by-step instructions available [here](http://clonezilla.org/clonezilla-live-doc.php). I chose the disk-to-disk clone option, and after tweaking the options a bit, was able to recover most of the hard disk. There were a number of clusters that CloneZilla complained about not being able to recover, but it seems they are not in any files that I use on a regular basis.

Lessons learned from this:

  1. Make sure you always have a backup. I use Carbonite, but there are several other great options out there.
  2. Use Spinrite for maintenance, and not for diagnoses. It may work in the ultimate attempt for recovery, but it's better to know in advance your disk is failing, than to be notified by Windows and then scramble around.
  3. Don't use the disk that is failing, get a duplicate disk as soon as possible, and use CloneZilla to copy your whole installation.

