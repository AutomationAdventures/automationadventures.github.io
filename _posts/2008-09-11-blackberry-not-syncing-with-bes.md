---
id: 197
title: Blackberry not syncing with BES
date: 2008-09-11T12:25:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=197
permalink: /2008/09/blackberry-not-syncing-with-bes.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2008/09/blackberry-not-syncing-with-bes.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/4604985178805598163
categories:
  - blackberry
  - calendar
  - enterprise
  - mail
  - pearl
  - schedule
  - synchronization
  - task
  - Telecom
---
For about a week now I've had problems synchronizing my Blackberry Pearl 8130 from Verizon with our Blackberry Enterprise server. Nothing synchronizes: email, calendar, to-do lists, etc.

After trying several options suggested around the net (take out battery, turn wireless synchronization off and back on), with no results, I thought I'd have to secure wipe my Blackberry again. Hesitating to do that, I was playing around with the phone last night, and noticed that the message folder for my enterprise mail was missing. Now completely convinced I had to bite the bullet and wipe the phone, I went off to a restless night of sleep.

This morning, I was browsing through some of the options in Settings, and I noticed in Security Options an entry named Firewall. Curious, I selected it. It showed the firewall enabled, gave me options to block certain incoming messages, and showed how many messages were blocked because of Incorrect Encryption keys. 1159 were blocked??? This gave me an idea: I've had problems surfing to certain sites with the browser, while others worked fine, or were slightly slower than normal. I reset the counter of blocked messages, and try to access one of the sites I had problems with (www.zoho.com). Sure enough, it didn't work, but upon checking the Firewall option, it now showed me 1 blocked message. Hey! Some key is corrupt!!!

The fix turned out to be very simple:

  * Go to Options
  * Go to Security
  * Go to General Settings
  * Scroll to the bottom where the Services are listed
  * Place your cursor on Desktop
  * Click the menu key and select Regenerate Encryp...

Not only did this allow me to surf to pretty much any site I had problems with before, my phone went through an automatic activation and showed me it was now synchronizing again with our Blackberry Enterprise server.

A fairly quick and simple fix, that is much faster than completely wiping your phone, and go through a new Enterprise Activation.