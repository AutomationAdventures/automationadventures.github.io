---
id: 390
title: Stupid programmers and the neutral zone
date: 2004-11-29T13:25:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=390
permalink: /2004/11/stupid-programmers-and-the-neutral-zone.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2004/11/stupid-programmers-and-neutral-zone_29.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/1402048080147864030
categories:
  - Network
  - X10
---
Isn't a holiday weekend great? I finally had some time to sit down and see what happens with all those triggers and programs that I wrote. After all, I still had the problem that sometimes the lamp in the living room would react to X10 signals, and sometimes it wouldn't. And this seemed to be the only item.

## Stupid Programmers

When I started analyzing the log file, it looked like the lamp never reacted to the button macros. All the other lights did, but when you look at the log file for the living room lamp, there was no entry that it had been turned off or on by that button macro. That narrowed it down: I probably forgot to reload the code.

After reloading the code, it still wouldn't respond. Well, maybe I need to do a force reload. That would be the sure-fire way to reload the code (which looked absolutely fine!). Still no go. Desparation was setting in at that point: I didn't get any error messages, so I thought everything was fine. Or wasn't it?

The setup that I have has a separate Linux box taking care of the MisterHouse program. I use a browser on a Windows box to tell MisterHouse to reload code. This triggers the program on the Linux box to start reloading and compiling stuff. And that's where the error messages are displayed: not in an error log, not on the window displayed when you reload the code - but on the screen where MisterHouse is sending the output.

And sure enough - there was an error. When adding the code to turn the living room lamp on and off by pressing a button, I also added some code I wanted to use for an outdoor light. However, the outdoor light was not defined yet. So, MisterHouse complains that I'm using a variable that hasn't been defined, and reuses the previous version of the code. Which didn't include my living room lamp.

I quickly commented out the section with the outdoor light, and forced a reload. Presto! There were no more error messages. And when I tested out the buttons, everything worked like it should.

## The Neutral Zone

I had bought a [ToggleLinc PLC switch](http://www.smarthome.com/23895.html) to control one of our outside lights. After resolving the erratic living room light, I was confident that we didn't have any more X10 signal issues. So, what do you do when you have a working system? Right: you change it.

I added the ToggleLinc in the garage, and fixed a logic problem at the same time (the switch closest to the house controlled the outside light, the one fartest away controlled the garage light - I think it should be reversed). So, armed with screwdriver, flashlight, and new switch, I set out to install the ToggleLinc.

It was pretty straightforward. The only thing that threw me off was that there were two black wires attached to the old switch. Hmm. One is supposed to be the Live wire, the other is the Load wire. That's when I found out I was missing one tool: a Volt meter.

The first attempt didn't work: the little green LED didn't come on. Maybe I had the wrong black wire designated as Live. So I switched the two black wires around. Still no go. Scratch head, check connections. Everything looks OK. The two black wires connected to Live and Load, the Ground wire connected, the Neutral wire capped. Just like the drawing. Hmm... the drawing does show the Neutral wire with dashes - making me believe it was an optional connection. Well, not according to the troubleshooting section:

  * "My switch only has two wires"
  * "Won't work - you need the Neutral wire, or you need to use a [SwitchLinc](http://www.smarthome.com/23885w.html)."

Luckily the neutral wires were there, just bunched up together at the back of the box. I hooked up the Neutral wire to them, and lo and behold - everything worked. Programming the switch with the correct address was a snap, and now we have a porch light going on at dusk and turning off at dawn.