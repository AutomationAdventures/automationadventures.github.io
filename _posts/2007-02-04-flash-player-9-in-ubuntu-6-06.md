---
id: 314
title: Flash Player 9 in Ubuntu 6.06
date: 2007-02-04T10:33:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=314
permalink: /2007/02/flash-player-9-in-ubuntu-6-06.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/02/flash-player-9-in-ubuntu-606_04.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/4637814611478755838
categories:
  - Linux
---
A couple of weeks ago Adobe released Flash 9 for Linux. I've looked around the net a bit to find instructions for installing it in Ubuntu, but some were pretty obscure (download the .rpm, convert it to .deb with alien, install the .deb package, ignoring the errors, etc.), and most were still for the beta player.

Luckily Adobe made it very easy: the tar.gz package includes an installer, and you can either install it only for the current user, or system-wide.

Here are the steps I took:

1. Download the .tar.gz archive from [here](http://fpdownload.macromedia.com/get/flashplayer/current/install_flash_player_9_linux.tar.gz)
2. Unpack it locally by issuing the command  
`tar zxvf install\_flash\_player\_9\_linux.tar.gz`
3. Go to the newly created directory:  
`cd install\_flash\_player\_9\_linux`
4. The Readme.txt file is your best source of information, and you should check it in case anything has changed. Basically it tells you to run flashplayer-installer.
5. If you want to do a system-wide installation, run  
`sudo ./flashplayer-installer`  
If you want to do an installation for the current user only, just use  
`./flashplayer-installer`  
I did a system-wide install - if you do it for current user only, I assume the prompts are similar, it just wants to know your local plugin directory.
6. The installer will tell you in which mode you are running (system-wide or current user), and then prompt you to either press CTRL-C to abort, or ENTER to continue
7. The only question asked for the system-wide installation is the directory that Firefox is installed in. Answer `/usr/lib/firefox`.
8. The installer will summarize what it will do, and then asks you to proceed. Type `y`.
9. You're done! Tell the installer that you don't want to do another install.

Pretty straightforward, and very similar to the original Flash Player 7 install that I did. So far it seems to be running fine!