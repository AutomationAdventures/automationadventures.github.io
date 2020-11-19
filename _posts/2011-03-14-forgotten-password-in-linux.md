---
id: 75
title: Forgotten password in Linux
date: 2011-03-14T08:00:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=75
permalink: /2011/03/forgotten-password-in-linux.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2011/03/forgotten-password-in-linux.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/1918253238995315915
image: /wp-content/uploads/2011/03/Padlock.jpg
categories:
  - Features
  - hack
  - Linux
  - password
  - reboot
---
![Picture by Freddie the Boy](/wp-content/uploads/2011/03/Padlock.jpg)

It happens to me every so often, that I have to do maintenance on a Linux box, and I've changed my passwords around and can't remember the password I used on that particular box (or even the user name...). I always have to hunt around the net, hoping I find something, so I thought I'd capture it on my own blog:

  1. Reboot the computer
  2. At the GRUB or LILO prompt, press escape.
  3. Go to the line that would normally boot, and press e to edit
  4. Go to the end of the command line, and add _rw init=/bin/bash_ to it
  5. Press Enter, then press b to boot
  6. You should now be entered into a passwordless root shell
  7. Either set your password with `passwd <username>`, or see a list of users with `cat /etc/passwd`.
  8. Reboot again
  9. Happy times!

Hope this helps me (and maybe some else) in the future...