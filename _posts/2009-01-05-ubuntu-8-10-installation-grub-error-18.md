---
id: 185
title: 'Ubuntu 8.10 installation - GRUB error 18'
date: 2009-01-05T12:25:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=185
permalink: /2009/01/ubuntu-8-10-installation-grub-error-18.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/01/ubuntu-810-installation-grub-error-18.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/1719673897602879030
categories:
  - "8.10"
  - error 18
  - grub
  - ibex
  - installation
  - intrepid
  - Linux
  - partition
  - ubuntu
---
Over the Christmas break I've installed Ubuntu 8.10 on my main machine. The installation was not upgradeable without some serious wizardry (the /boot partition was too small, and increasing that on a full disk is not easy), so I decided to do a fresh install.

After going through all the installation steps, and booting up Ubuntu 8.10 for the first time, I was greeted with a GRUB error 18. Some Googling revealed that this was caused by the hard disk being too large for the BIOS to handle. And there was even a helpful post that described a three step process:

  * Set your hard disk for LBA mode
  * Install Ubuntu
  * Set your hard disk back to normal

<div>
  Unfortunately, this didn't work for me. The installation resulted in the same GRUB error. However, there is an easier fix.
</div>

<div>
</div>

<div>
  GRUB error 18 means actually that the kernel cannot be found in the first 1023 cylinders. You can change that by creating a /boot partition that is completely within those first 1023 cylinders. So, after the first try at installing, and failing with the GRUB error, try this:
</div>

  * Restart your machine, with the Ubuntu CD as startup.
  * Install Ubuntu as normal, until you get to the partition information.
  * Select Manual from the partition options.
  * The only thing you need to change is the main partition (/). Delete the one that is on the disk now. The partitioner may tell you it needs to write changes to the disk - by all means, let it write them.
  * Next, create a partition at the very beginning of the hard disk, of sufficient size, but not too big (I decided on 1GB, but it may be better to go with 512KB or even smaller - not too small, since I couldn't do an upgrade on my 128KB boot partition). Choose ext2 as file system - you won't need journaling or anything fancy on that partition. Your mount point is /boot.
  * Finally, create the main partition, covering the remainder of the hard disk. Make the file system ext3 - you want the journaling etc. on this one.
  * You should now have a /boot partition at the beginning of your disk, a / partition for most of the rest, and a small swap partition (about twice the size of your memory). If not, you need to manually adjust the partitions until you have all three.
  * Continue with the rest of the installation.

<div>
  Your mileage may vary, but this worked for me (it's also the trick I used when installing 6.06LTS). Hope this helps someone!
</div>