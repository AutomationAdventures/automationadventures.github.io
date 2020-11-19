---
id: 200
title: Google Chrome available for download
date: 2008-09-08T13:26:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=200
permalink: /2008/09/google-chrome-available-for-download.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2008/09/google-chrome-available-for-download.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/9085704965834965941
image: /wp-content/uploads/2008/09/googlechrome.jpg
categories:
  - beta
  - browser
  - chrome
  - google
  - Network
  - Productivity
  - Windows
---
![Chrome Beta Browser](/wp-content/uploads/2008/09/googlechrome.jpg)

Google has released their beta browser <a href="http://www.google.com/chrome" target="_blank">Chrome </a>for Windows. It distinguishes itself from other browsers by having a very minimalistic design, and some interesting technological features:

  * The address bar doubles as a search box, history browser and suggestion bar.
  * The tabs can be dragged out of the browser to create a new window, or multiple tabs can be combined into one window.
  * The new sandbox feature allows every tab to run independently from the other tabs, so if one site crashes it won't take anything else down, and can confine "bad" sites to just their sandbox (instead of giving them access to your whole machine as in some browsers made in the Northwest of the USA).
  * Activating the Incognito mode will prevent any pages you visit from showing up in your history.
  * Chrome has improved warnings for suspected phishing sites, malware, etc.
  * By clicking the star icon next to the address of a website, it is turned into a bookmark.
  * It features Google Gears integrated in the browser.
  * The Javascript engine is one of the fastest available today.
  * Chrome is multi-threaded. Not only does this mean that one looping JavaScript will no longer tie up your whole browser, it simplifies memory management (since the separate process can be closed, and release all used memory), and can make use of multiple processors.
  * Google continually updates a list of harmful sites, that Chrome uses to warn the user.

After all these benefits, there are some negatives:

  * I couldn't run the Chrome browser out of the box. Whenever I started it, it would give me "The application failed to initialize properly (0xc0000005). Click on OK to terminate the application.". A bit of Googling taught me that Symantec doesn't like the sandbox option of Chrome. If you add _-no-sandbox_ to the shortcut used to launch Chrome, all is well (except you're not using the sandbox feature).
  * Limited plugin availability. Since the browser is pretty new, there aren't a lot of third party, or even first party, add-ons, as opposed to Firefox.
  * The end user license. Although Google's motto is "Do no evil", some of the wording in the EULA suggests that Google has rights to do anything it wants with whatever you enter through the browser. This sounds like Adobe's EULA for Photoshop Express, and hopefully Google will revise the license to be more respective of the user's ownership.
  * Beta. I know Google has a history of releasing beta products (I think GMail just recently left beta status), but this time, the playing field is different. This is the frontline of the battle against intrusions, this is where the new malware tries to enter your computer. If there is a hole in Chrome, the bad guys will exploit it - especially since Google is a pretty high-profile target.
  * Fear of lock-in. Soon you'll be using GMail, Google Docs, Google Calendar, Google Spreadsheets, etc., all through your Google browser... One company to rule them all?

It will be interesting to see where Google takes Chrome, and if acceptance is going to be as high, or even higher, as Firefox.

If you want to try it, go to <a href="http://www.google.com/chrome" target="_blank">Google Chrome</a> and download your copy.