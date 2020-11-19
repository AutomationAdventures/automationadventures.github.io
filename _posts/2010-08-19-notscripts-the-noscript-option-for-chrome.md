---
id: 124
title: 'NotScripts - The NoScript option for Chrome'
date: 2010-08-19T17:15:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=124
permalink: /2010/08/notscripts-the-noscript-option-for-chrome.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2010/08/notscripts-noscript-option-for-chrome.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/589998026537517037
image: /wp-content/uploads/2010/08/NotScripts.png
categories:
  - chrome
  - javascript
  - noscript
  - notscripts
  - Software
---
Tuesday the 18th of August a Google Chrome plugin called [NotScripts](https://chrome.google.com/extensions/detail/odjhifogjcknibkahlpidmdajjpkkcfn) was released that makes controlling which JavaScripts, IFrames and plugins run in your browser a whole lot easier. [NotScripts](http://optimalcycling.com/other-projects/notscripts/) is developed by Eric Wong on the [Optimal Cycling](http://optimalcycling.com/) website.

Before this plugin, you were forced to use the Chrome Option to disable JavaScript, and selectively allow sites to run JavaScripts. However, when you enabled it for a site, everything that that site sent to you was enabled - including potentially harmful third party sites using JavaScript. It is possible to dive into the settings and enable some sites while disabling any malicious websites, but it was far from user friendly. I desperately missed the [NoScript](http:) from Firefox. So desperately, that in some cases I went back to Firefox to make sure I wouldn't be exposed to any JavaScripts I didn't like.

![NotScripts](/wp-content/uploads/2010/08/NotScripts.png)

After installing NotScripts, a little pyramid icon appears in your address bar, to the left of the bookmark button. Clicking it shows a list of all the sites that try to run scripts on the page you're viewing. You can enable them one by one, or temporarily allow scripting globally. When at least one site is enabled, the pyramid now gets a green square over it.

The installation requires you to modify a file deep in the bowls of your computer. The file contains a password used to encrypt the settings from NotScripts, as they are stored in an area accessible by any site you're visiting. So to prevent tampering with the file, it's encrypted. I think in later versions this may be controlled with a settings option, to make it user friendlier. Then again, this is a one-time option, so it's not too invasive.

![Part of the NotScripts option page, with password enabled](/wp-content/uploads/2010/08/NotScriptsOptions.png)

NotScripts is open source and is released under the GNU General Public License v3. Development is continuing (version 0.9.1 was released the 18th, one day after 0.9.0!), and the author is asking for donations to continue development.