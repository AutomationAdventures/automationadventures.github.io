---
id: 177
title: Upgrade Ubuntu server 6.04 LTS to 8.04 LTS
date: 2009-02-23T21:37:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=177
permalink: /2009/02/upgrade-ubuntu-server-6-04-lts-to-8-04-lts.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/02/upgrade-ubuntu-server-604-lts-to-804-lts.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/4812270293890985862
categories:
  - Linux
---
When upgrading an Ubuntu server to 8.04 LTS, you should use the new and improved server upgrade system. Use the following steps to activate this upgrade process:

  1. Enable the "dapper-updates" repository
  2. Install the "update-manager-core" package. Dependencies include python-apt, python-gnupginterface and python2.4-apt.
  3. Run the command "sudo do-release-upgrade" in a terminal window
  4. Follow the prompts on-screen.