---
id: 304
title: 'How to stop Windows vulnerabilities before they are known - with DEP'
date: 2007-03-10T12:00:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=304
permalink: /2007/03/how-to-stop-windows-vulnerabilities-before-they-are-known-with-dep.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/03/how-to-stop-windows-vulnerabilities_10.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/9194968940005528263
categories:
  - Linux
  - Windows
---
Most Windows XP users are unaware about a very powerful option included in Service Pack 2, called Hardware DEP support. DEP stands for Data Execution Protection, and can prevent many buffer overruns that plague Windows (and Linux, and Apple) software.

To activate hardware DEP, you need two things:

  1. A processor that supports DEP
  2. An operating system that implements DEP

Most processors produced in the last couple of years support it. However, most BIOSes turn DEP off by default! To find out if your system supports hardware DEP, [Steve Gibson](http://www.grc.com/) of Spinrite fame has written a small Windows utility called [Secureable](http://www.grc.com/securable.htm). This will show you processor bitlength, Hardware DEP support, and Hardware Virtualization support. I haven't seen any utilities for Linux...

After determining that your processor supports Hardware DEP, you need to enable it. Reboot your computer, and go into the setup. Depending on the BIOS, this may or may not show up as an option. Dig around in the menus, but be careful not to turn any other options on or off besides Hardware DEP.

If your BIOS allows you to turn DEP on, reboot the computer again, and turn DEP on in Windows. It's a little hidden, but I reached it as follows:

1. Right-click on My Computer and select Properties
2. Click on the Advanced tab
3. In the Performance block, click on Settings.
4. Click on the Data Execution Prevention tab
5. Select the radio button Turn On DEP.

If any programs cause problems, you can add them to the exceptions list by pressing the Add button in the DEP tab, and adding the program name.

**Warning! There are reports of Windows not being able to start after enabling DEP. Check out Steve Gibson's [Securable](http://www.grc.com/securable.htm) page for the status of his program DEPuty and links to a [Microsoft Knowledge Base article](http://support.microsoft.com/kb/875352) on how to set up DEP.**

However, since the advantages of DEP are pretty big, I suggest making a backup of your system and trying it out, despite the risks. If you are a little more conservative, wait until Steve finished DEPuty...