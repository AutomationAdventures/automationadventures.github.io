---
id: 315
title: Ubuntu 6.06 LAMP server install
date: 2007-01-30T14:54:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=315
permalink: /2007/01/ubuntu-6-06-lamp-server-install.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/01/ubuntu-606-lamp-server-install_30.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/7324231904554497103
categories:
  - Linux
  - Network
---
Last Friday our first 'official' Linux server went live at work. It's a 6.06 LAMP server installation, which was remarkably smooth. The main problem was trying to figure out why the Compaq Proliant ML370 would hang after pretty much the first line on the screen (unpacking the kernel) and giving a cryptic 4294672.157000 error message. It turns out there is a problem with the APIC support in Ubuntu 6.06, and adding the option noapic on the command line before the last - is the solution.

The rest of the installation was like I said remarkably smooth. We're setting up a Wiki on the server, and transferring it from our Fedora Core 4 testserver was pretty easy (it would have been real easy if I'd remembered to fix some hard coded paths).

Next steps are setting up a virtual webserver, so we can access the site as wiki.medeco.com, and enhancing the security... 🙂