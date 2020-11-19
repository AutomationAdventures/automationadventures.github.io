---
id: 173
title: 'Nagios - how to determine the name of a service in Windows'
date: 2009-03-27T11:35:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=173
permalink: /2009/03/nagios-how-to-determine-the-name-of-a-service-in-windows.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/03/nagios-how-to-determine-name-of-service.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/1640545993235553749
categories:
  - client
  - Linux
  - monitor
  - nagios
  - Network
  - Security
  - service
  - Windows
---
I've recently set up <a href="http://www.nagios.org/" target="_blank">Nagios </a>on one of our test servers, and the <a href="http://sourceforge.net/projects/nscplus" target="_blank">Windows client</a> for Nagios allows you to monitor services (whether they started, stopped, etc.). However, the name of the service to monitor isn't always the same as the name in the Services application in Administrative Tools.

To find out the name of the service, you'll have to look at the registry:

  1. Open up regedit (Run, regedit)
  2. Navigate to HKEY\_LOCAL\_MACHINE
  3. Navigate to SYSTEM
  4. Navigate to CurrentControlSet
  5. Navigate to Services
  6. Find the service you plan on monitoring. The name of the node is the name you need to enter on the Nagios server as the name of the service.