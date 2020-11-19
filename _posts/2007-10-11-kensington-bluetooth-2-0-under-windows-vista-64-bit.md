---
id: 269
title: Kensington Bluetooth 2.0 under Windows Vista 64-bit
date: 2007-10-11T15:19:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=269
permalink: /2007/10/kensington-bluetooth-2-0-under-windows-vista-64-bit.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/10/kensington-bluetooth-20-under-windows.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/7734769939943683865
categories:
  - 64-bit
  - bluetooth
  - kensington
  - Network
  - Telecom
  - vista
  - Windows
---
I finally got my Bluetooth adapter ([a Kensington Bluetooth USB Adapter 2.0](http://us.kensington.com/html/9403.html)) working. Initially when I bought it, trying to install the factory supplied driver wouldn't work. After a tiresome exchange with support, where they informed me that there was no Vista driver available, and they didn't have any information about whether or not the driver would be developed.

Well, [apparently they developed one](http://us.kensington.com/html/1492.html) (yay Kensington), but failed to inform people who had filed a request for it (Booh! Hiss!). However, when I tried to install it, everything seemed to work fine until a message box popped up informing me that the installation had failed. Digging through the Vista Temp directory, I found the installation log, with one Error message (the rest was fine): "ERROR Device plugged in, no MS stack".

After trying to run the installation program with Administrative rights, and with UAC turned on and off, I was ready to give up. The funny thing was that the installation program just seemed to download the actual installation program, explode it, run the setup program in there, and delete it when it finished or failed. So, during a new attempt, I grabbed the directory that the installation program created. It has the platform specific files (in my case 64-bit), a setup program and some other stuff. Of course, the installation failed again, but at least I had the files now.  
**Update:**The files are located in Users[you]AppDataLocalTempBTW_6.0.1.6200.

When I pulled up the Device Manager in Vista, it showed the Bluetooth EDR dongle listed. I tried several different things (which I won't mention, because they didn't work), until I decided to Update the driver for the dongle. When Vista asked me for the driver, I pointed it to the driver directory within the exploded installation directory, and Vista was happier than a clam to install a bunch of devices (Kensington Bluetooth EDR Dongle with trace filter, Microsoft Bluetooth Enumerator, and two Bluetooth devices in the Network adapters group). Yay!

The next (and last) step in setting up the adapter with my Motorola RAZR was the easiest: go to Control Panel, Bluetooth Devices, and Add a new device. Make sure your phone is discoverable, and set up a passkey. Voila! The phone should now be connected.

Next thing on the list is trying to grab [floAt's Mobile Agent](http://fma.sourceforge.net/). I have an older version installed, and have already figured out that the only way floAt can talk to my phone seems to be to use the COM port (when you pull up Bluetooth Devices, click your phone, select Properties, and go to the Services tab, it will tell you which COM port the phone uses).