---
id: 183
title: Ubuntu 8.10 connect to Cisco VPN through vpnc
date: 2009-01-07T12:30:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=183
permalink: /2009/01/ubuntu-8-10-connect-to-cisco-vpn-through-vpnc.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/01/ubuntu-810-connect-to-cisco-vpn-through.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/3895576600180640232
image: /wp-content/uploads/2009/01/screenshot-network-connections.png
categories:
  - "8.10"
  - cisco
  - ibex
  - intrepid
  - Linux
  - Network
  - ubuntu
  - vpn
  - vpnc
---
One of the things I need to do with my home machine is occasionally connect to our VPN at work. In 6.06LTS this required downloading the Cisco VPN client, compile it, install it, and hope it will work in the next kernel update. On top of that, you had to run a script to create the VPN connection.

In 8.10 Intrepid Ibex this is much simpler, and much more elgant. First, you need to install the VPN Connection Manager (VPNC) package. When you do this through the Add/Remove Applications, it should install three packages:

  * vpnc
  * resolvconf
  * network-manager-vpnc

  The first two are essential, but the third one is the kicker in 8.10: it allows you to manage your VPN certificates, and choose which connections to make and break.

  After you've installed these three packages, do the following:

  * right-click on the Network Manager applet.
  * Choose Edit connections
  * Click the VPN tab
  * You should have the options to Add a connection manually, or to Import a VPN certificate. ![Screenshot Network Connections](/wp-content/uploads/2009/01/screenshot-network-connections.png)

  * Since our network admin provided me with a certificate, I chose Import, and selected the certificate file.
  * The import will try to get as much information as possible out of the selected file. In most cases, you need to provide the group and user password.
  * If the group password is encrypted, it can be determined by taking the encrypted string and running it through the Cisco decoder at http://www.unix-ag.uni-kl.de/~massar/bin/cisco-decode
  * Save your changes ![Screenshot connection](/wp-content/uploads/2009/01/screenshot-connection.png)
  * Close the Edit Connections screen

  You should now be able to left-click on the Network Manager applet, select VPN connections, and click on the newly added connection. The Network icon will show a circling star for a couple of seconds, and then indicate that the VPN connection is established by showing a yellow padlock in the bottom right of the icon.

Disconnecting is just as easy: left-click on the applet, select VPN connections, and select Disconnect VPN.