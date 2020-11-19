---
id: 312
title: Intel Ethernet Pro 100 on Ubuntu
date: 2007-02-21T17:08:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=312
permalink: /2007/02/intel-ethernet-pro-100-on-ubuntu.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/02/intel-ethernet-pro-100-on-ubuntu.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/6414223210095607257
categories:
  - Linux
  - Network
---
Well, our wiki server is up and running, and cyclops is humming along. However, it seems a little sluggish and it turns out [Backup Exec](http://www.backupexec.com/) is backing it up at the tremendous transfer rate of 2MB per **minute**....

That's kind of slow. Backing up all of the server will take about 16 hours that way. And it is something in that machine, because the old test server (a HP XW4200) is reaching about 300+MB per minute in the same setup. I'm thinking that it is a network card issue, but I'm not sure what to do to solve it. So, I've started a [thread](http://www.ubuntuforums.org/showthread.php?t=365500) in the [Ubuntu forums](http://www.ubuntuforums.org/index.php), with little response so far. Basically I'm answering my own question... 🙂

If anyone has any experience with setting up Ubuntu or Debian or Linux on the Proliant M370, feel free to leave a comment...

Oh, and don't add the option `options e100 e100\_speed\_duplex=4` to /etc/modprobe.d/options - your machine will take forever to boot up to a prompt, and it will not enable the network card. Apparently that's not a valid option for my card or driver...