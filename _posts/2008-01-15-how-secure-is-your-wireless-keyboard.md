---
id: 250
title: How secure is your wireless keyboard?
date: 2008-01-15T14:21:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=250
permalink: /2008/01/how-secure-is-your-wireless-keyboard.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2008/01/how-secure-is-your-wireless-keyboard.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/5668962390811855316
categories:
  - cracked
  - dreamlab
  - keyboard
  - microsoft
  - Network
  - Security
  - Windows
  - wireless
---
So, with all the dangers lurking out there, we all use https connections to our servers, have SSL sessions, use PGP keys to sign and encrypt our email, and run a plethora of scanners to keep our computers virus- and adware-free. But how about a keylogger that picks up your wireless keyboard transmissions?

This is not a new problem. A man in Norway [saw his neighbor typing on his screen](http://www.aftenposten.no/english/local/article427668.ece), because his wireless keyboard's receiver was picking up his neighbor's keyboard. In this case it was the same brand computer, and the same brand wireless keyboard. Encryption would prevent that from happening. But now that the [Swiss security firm DreamLab Technologies](http://www.dreamlab.net/) has [discovered](http://www.dreamlab.net/news/dreamlab-cracks-wireless-keyboard-encryption) that the popular Microsoft Wireless Keyboards use an encryption that can be cracked by a simple PDA, using even a so-called secure wireless keyboard becomes a serious security risk.

In the [white paper](http://www.dreamlab.net/download/articles/Press%20Release%20Dreamlab%20Technologies%20Wireless%20Keyboard.pdf) mentioned in the press release, the two researchers describe in broad terms what happens between a wireless keyboard and the receiver, and how easy it is to eavesdrop on a session. The frequency used is in the 27MHz band, for which a large number of receivers is available. Most keyboards should have only a limited range, but under the right circumstances and with the right antenna distances of a mile have been achieved.

Not all wireless keyboards have the same problems, however. Logitech uses a different technology to encrypt the communication between keyboard and receiver. Also, Bluetooth keyboards are possibly more secure. The two researchers (Max Moser and Philipp Schroedel) are continuing to investigate the security of the different wireless keyboards.

In the mean time, I suggest not using your wireless keyboard for anything but the most innocent of traffic. If you want to control your media center with it, that's fine. Just don't go online with your bank, without hooking up a keyboard cable.

There is a [demo video](http://www.remote-exploit.org/max/automated.html) on the Dreamlab Technologies website, showing their exploit in action. Within a minute the viewer is watching two different keyboards being picked up and cracked.