---
id: 244
title: Spam filtering in Windows Outlook
date: 2008-03-03T17:48:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=244
permalink: /2008/03/spam-filtering-in-windows-outlook.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2008/03/spam-filtering-in-windows-outlook.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/5646160541103314149
categories:
  - outlook
  - plugin
  - Productivity
  - spam
  - spambayes
  - Windows
---
Over the weekend, our company's spam filter decided it would no longer filter spam. Naturally, this never happens on a weekday, so this morning everybody's Inbox was overflowing with Viagra and Rolex offers... and the lucky few who have a SmartPhone got all that spam earlier than the rest of us.

Since the corporate spam filter was a piece of crock anyway (I won't name names because it was Symantec), I decided to look around for a good Outlook spam filter. I came across [SpamBayes](http://spambayes.sourceforge.net/).  
<a name='more'></a>  
SpamBayes is a free, open-source spam filter, that uses the Bayesian approach to determining if a message is spam or ham. A message scores points in both the ham and the spam category, based on the hamness or spamness of each word in the message body. There is a gray area where SpamBayes will let the user know a message is suspected Spam, and there are setting to determine whether a message is certainly spam or certainly ham. The SpamBayes website has a [detailed description](http://spambayes.sourceforge.net/background.html) of the inner workings of the algorithm, so I won't go into too much detail.There are a number of different applications of SpamBayes. The one probably most commonly used is as an Outlook plug-in (that's what I was looking for). The plug-in supports Windows XP with Outlook 2000/2003/2007, and Windows Vista with Outlook 2003/2007. Other applications include setting it up on Thunderbird, Gmail, and any POP3 or IMAP mail client, or installing a script that runs on your mail server.The installation as an Outlook plugin was fairly painless, even on a Windows Vista 64 box. The only problem I encountered was that Outlook immediately crashed after installing SpamBayes, and the plugin was disabled when I restarted Outlook. However, the [FAQ page](http://spambayes.sourceforge.net/faq.html) quickly gave me a solution (tell DEP that Outlook is a safe application - I reluctantly agreed), and SpamBayes has been humming along ever since.

After installation, SpamBayes runs a setup wizard, which basically asks you to feed it a large amount of spam and a large amount of ham. This will get the algorithm started. You can then tweak SpamBayes to look in certain folders (I currently get GMail in Outlook, so I have two inboxes). When SpamBayes detects spam, or suspects it, you can tell it what to do. I currently have configured it so that spam is moved to the Junk E-mail folder and marked read, and suspected spam to the Junk Suspects folder and marked unread.

Personally I think SpamBayes does a better job than the Symantec Spam filter (that seems to run every now and then) - it correctly detects all the spam Symantec has detected, and then some. We'll have to see how it behaves in the long run, but for now I'm not shedding any tears about the demise of Enterprise Spam detection.