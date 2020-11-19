---
id: 253
title: Outlook refuses to open messages attached to another message
date: 2007-12-21T13:09:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=253
permalink: /2007/12/outlook-refuses-to-open-messages-attached-to-another-message.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/12/outlook-refuses-to-open-messages.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/2632130130727154531
categories:
  - attachment
  - desktop
  - email
  - google
  - outlook
  - Productivity
  - Windows
---
I ran into a problem with Outlook the other day. Someone sent me a message, that was a forwarded message from someone else. Only, the forwarded message was attached, instead of quoted. And Outlook refused to open the message. Double-click, Right-click & Open, Right-click & Save, nothing worked (although Save gave me a beautiful .msg file - that Outlook refused to open).

After searching the Internet for a couple of days, seeing all kinds of references to security levels and warning messages (that I didn't get - Outlook didn't give a peep when trying to open the message), I gave up - I only get one or two attached messages a month, and most of them are jokes.

It got annoying however when I decided to use the GTD Outlook Plug-in. In this plug-in, you have the capability to attach several messages to a Task. The message that initiated the Task is quoted in the task description, and subsequent messages are attached. I couldn't open these attachments, and to make things worse, the GTD Plugin moved the messages that I attached to an undisclosed location, so I couldn't find these messages anymore!

So, back to searching the Internets. I finally came across [this message](http://www.tutorials-win.com/Outlook/Cant-open-595679/) on [Tutorials Win](http://www.tutorials-win.com/). It described a similar problem with Outlook 2007 (I'm still using 2003), and said that Google Desktop was to blame. That made sense: a couple of days ago Windows Vista informed that Google Desktop had unexpectedly quit. The forum post suggested disabling the indexing of Outlook, but for me, the only thing that worked was completely uninstalling Google Desktop.

Everything works fine now, I can access my attached email messages again. I'm sure I'll miss Google Desktop, though...