---
id: 178
title: 'My webpage is covered by something! - ga_shade hides your website'
date: 2009-02-16T12:27:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=178
permalink: /2009/02/my-webpage-is-covered-by-something-ga_shade-hides-your-website.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/02/my-webpage-is-covered-by-something.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/1156640480117100645
categories:
  - analytics
  - css
  - div
  - ga_shade
  - google
  - Miscellaneous
  - page
---
I recently ran into some trouble accessing Automation Adventures. A strange screen covered pretty much the first page of the website, neatly hiding the login button and the dashboard of WordPress. Some digging revealed that Google Analytics had added a CSS division named ga_shade, effectively preventing me from using my own site...

Luckily, the fix is simple: remove the GASO cookie. In Firefox, open Tools, Options, Privacy, and click on the Show Cookies button. In the Search bar, type GASO, and remove the cookie. Reload the page, and the mist should be gone.