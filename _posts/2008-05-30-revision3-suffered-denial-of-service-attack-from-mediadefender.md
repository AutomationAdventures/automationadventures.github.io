---
id: 218
title: 'Revision3 suffered Denial of Service attack from... MediaDefender?'
date: 2008-05-30T12:18:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=218
permalink: /2008/05/revision3-suffered-denial-of-service-attack-from-mediadefender.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2008/05/revision3-suffered-denial-of-service.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/2926047276411379830
categories:
  - attack
  - dos
  - mediadefender
  - Network
  - revision3
  - Security
  - syn
  - video
---
<a href="http://revision3.com/" target="_blank">Revision3</a>, host of such video podcasts as <a href="http://revision3.com/diggnation" target="_blank">Diggnation</a>, <a href="http://revision3.com/systm" target="_blank">Systm </a>and <a href="http://revision3.com/tekzilla" target="_blank">TekZilla</a>, <a href="http://revision3.com/blog/2008/05/29/inside-the-attack-that-crippled-revision3" target="_blank">suffered a Denial of Service attack</a> over the Memorial Day weekend. The interesting twist in this is that Revision3 says <a href="http://www.mediadefender.com/" target="_blank">MediaDefender </a>was the one causing the <a href="http://en.wikipedia.org/wiki/Denial_of_Service" target="_blank">DoS</a> attack.

Why is this interesting? Because for years discussions have been going on about the moral and legal issues of remotely trying to patch a machine that is part of a zombie network. The strategy is using a similar technique as the controllers of the network use to tell their zombies what to do, but in this case it tells the zombies to patch themselves and "revive" them from zombiness. The main point of discussion is whether or not it is morally and legally correct to control someone else's machine, even if the purpose of that control is to fix a problem.

And here is MediaDefender doing that exact thing, with the disastrous end result that prevents anti-virus companies from employing the remote patch strategy. According to Jim Louderback's <a href="http://revision3.com/blog/2008/05/29/inside-the-attack-that-crippled-revision3" target="_blank">blog post</a> (CEO of Revision3), MediaDefender readily admits to using Revision3 servers for what they believe a good cause (distributing fake torrents to identify and neutralize illegal file sharing websites). The problem is, they never informed Revision3, who noticed the unknown torrents, identified them, and blocked access to them. At that point, the MediaDefender servers went postal, believing that some distributor had blocked them, and started a <a href="http://en.wikipedia.org/wiki/SYN_flood" target="_blank">SYN flood</a> on the Revision3 servers.

When Revision3 traced all this back to MediaDefender, there was no apology or anything. Just a statement saying that they now added a policy to prevent this from happening again. Which is perfectly fine, but what about the thought behind the original policy? What if this DoS was targeted against something more critical than Revision3's video distribution (not belittling Revision3), like a hospital, power plant or EMS station?

I hope Revision3 follows up on this. Apparently the FBI is involved (a DoS attack is illegal), and hopefully this will result in something more than a slap on the hand.

<u><strong>Update</strong></u>: Wired has <a href="http://blog.wired.com/27bstroke6/2008/05/mediadefender-d.html" target="_blank">blogged </a>about this as well.