---
id: 48
title: 'It''s not too late to change your Facebook password - is it?'
date: 2011-06-08T12:00:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=48
permalink: /2011/06/its-not-too-late-to-change-your-facebook-password-is-it.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2011/06/it-not-too-late-to-change-your-facebook.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/659282810970183132
image: /wp-content/uploads/2011/06/facebook.jpg
categories:
  - authentication
  - facebook
  - Features
  - firesheep
  - https
  - Miscellaneous
  - Security
---
![](/wp-content/uploads/2011/06/facebook.jpg)

For the last several years, ever since Facebook allowed third-party access to your data, your account with Facebook could have been taken over.

Not by [Firesheep](http://codebutler.com/firesheep) (although the principal is similar), but because of the third-party application actually leaking an access token outside of the conversation between you, Facebook and the third-party.

In a nutshell, the sequence of events allowing this are as follows:

  1. You're logged in to Facebook, and want to play a game (start up a third-party application)
  2. The third-party application presents a permission dialog page, where you allow the application access to your friends, your personal information, and posting on your wall.
  3. The third-party application gets an access token from Facebook, which allows it to do all these things without you having to explicitly give them permission every time.
  4. That token is exchanged with Facebook every time the third-party issues requests.

So far it is very similar to the Firesheep issue. However, the twist here comes if the third-party application uses a legacy Facebook API:

  1. The access token is sent as part of the URL
  2. The application requests resources from another site (such as an advertiser).
  3. The advertiser receives the referring URL, which contains the access token.

Now the advertiser has the access token that the third-party application uses, and can use that to do the same actions you allowed that application. Best case it now has a list of your friends, worst case you've just given the advertiser the right to post on your wall.

And since requests are normally logged, it is even possible that when the advertiser's site gets hacked, the hacker finds the log, containing these access tokens, and can do these same actions.

Symantec has [identified](http://www.symantec.com/connect/blogs/facebook-applications-accidentally-leaking-access-third-parties) this issue back in late April, and Facebook has [since then](https://developers.facebook.com/blog/post/497) [taken steps](https://developers.facebook.com/blog/post/499) to remedy this problem. However, none of these steps completely remedy the problem until September 1st, when the legacy API calls that allow this venue of attack are disabled, and replaced by OAuth.

So what can you do to prevent your account being used as a beach head of attack?

  1. Review what rights you've given to what applications, and delete rights you no longer use or think are unnecessary. This is done in Facebook under Account, Privacy Settings, Apps and Websites, Apps You Use.
  2. Insist on using HTTPS wherever you can, and think twice about third-party applications that do not support it.
  3. Change your password. Changing your password invalidates the previous security tokens.

Symantec states that to their knowledge no Facebook users were impacted by this issue. However, this is a definite possibility of attack, and a few good security principles can keep your account safe (or safer) from attacks.