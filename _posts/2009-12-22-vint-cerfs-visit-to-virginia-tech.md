---
id: 153
title: 'Vint Cerf''s visit to Virginia Tech'
date: 2009-12-22T12:33:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=153
permalink: /2009/12/vint-cerfs-visit-to-virginia-tech.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/12/vint-cerf-visit-to-virginia-tech.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/6583349780107505784
categories:
  - cellphone
  - cloud
  - Network
  - tcp/ip
  - vint cerf
---
I haven't written anything specific to the blog in about a month. That doesn't mean nothing interesting happened - far from it.

One of the interesting things was a speech by <a href="http://en.wikipedia.org/wiki/Vinton_Cerf" target="_blank">Vinton Cerf</a> at Virginia Tech. Apart from being an entertaining speaker, you may also know him as one of the inventors of TCP/IP (together with <a href="http://en.wikipedia.org/wiki/Robert_E._Kahn" target="_blank">Bob Khan</a>). He touched on a large variety of subjects, some of which I'd like to highlight here:

<span style="font-size: large;">There are 4 billion mobile phones, and 1 million PCs</span>

Of all these devices, about 25% are internet connected. And the mobile phone market is still growing. Basically, if you don't take mobile phones into account when developing software, you're missing out on a large portion of the internet connected public.

<span style="font-size: large;">Growing Internet penetration will radically change the landscape</span>

Internet penetration is the percentage of a country's population that can use the internet. The current top users of the internet are:

<table border="1">
  <tr>
    <th>
      Country
    </th>
    
    <th>
      Internet Users
    </th>
    
    <th>
      Penetration
    </th>
    
    <th>
      Users at 90% penetration
    </th>
  </tr>
  
  <tr>
    <td>
      China
    </td>
    
    <td>
      338.0
    </td>
    
    <td>
      26.9%
    </td>
    
    <td>
      1,130.9
    </td>
  </tr>
  
  <tr>
    <td>
      United States
    </td>
    
    <td>
      248.2
    </td>
    
    <td>
      74.1%
    </td>
    
    <td>
      301.5
    </td>
  </tr>
  
  <tr>
    <td>
      Japan
    </td>
    
    <td>
      94.0
    </td>
    
    <td>
      75.5%
    </td>
    
    <td>
      112.1
    </td>
  </tr>
  
  <tr>
    <td>
      India
    </td>
    
    <td>
      81.0
    </td>
    
    <td>
      7.0%
    </td>
    
    <td>
      1,041.4
    </td>
  </tr>
  
  <tr>
    <td>
      Germany
    </td>
    
    <td>
      54.2
    </td>
    
    <td>
      65.9%
    </td>
    
    <td>
      74.0
    </td>
  </tr>
  
  <tr>
    <td>
      Brazil
    </td>
    
    <td>
      50.0
    </td>
    
    <td>
      34.0%
    </td>
    
    <td>
      132.4
    </td>
  </tr>
  
  <tr>
    <td>
      United Kingdom
    </td>
    
    <td>
      46.7
    </td>
    
    <td>
      76.4%
    </td>
    
    <td>
      55.0
    </td>
  </tr>
  
  <tr>
    <td>
      Russia
    </td>
    
    <td>
      45.3
    </td>
    
    <td>
      32.3%
    </td>
    
    <td>
      126.2
    </td>
  </tr>
  
  <tr>
    <td>
      France
    </td>
    
    <td>
      43.1
    </td>
    
    <td>
      69.3%
    </td>
    
    <td>
      56.0
    </td>
  </tr>
  
  <tr>
    <td>
      South Korea
    </td>
    
    <td>
      37.5
    </td>
    
    <td>
      77.3%
    </td>
    
    <td>
      43.7
    </td>
  </tr>
</table>

(All user totals are in millions. Data as of Q2 2009. Source: <a href="http://www.internetworldstats.com/" target="_blank">Internet World Stats</a>)

So, currently China has the most users, followed closely by the US. If we'd get a 90% penetration rate in every country (and combine that with mobile phones - not all users have to use PCs!), we get a completely different picture: 1.1 billion Chinese, 1 billion Indians, followed by about 300 million Americans...

Even if you include all of Western Europe, you won't get half of the users that China has by itself. It would be wise to account for non-Western alphabets in any new products.

<span style="font-size: large;">IPv4 will run out of address space</span>

IPv4 will run out of available addresses somewhere in 2011, by the latest estimates. So it would be wise to adopt IPv6 in any new deployments.

<span style="font-size: large;">Inter-cloud communication is the new frontier</span>

Computing is moving more and more towards the "Cloud". However, we currently have several different clouds: Amazon, Google, IBM, etc. None of the clouds are interchangeable, and can't communicate with each other.

The next big step in computing would be to develop a method to let information from one cloud move to another, to reach its destination. Vinton Cerf likened the current situation to the computer networks before the invention of TCP/IP and the Internet: several different islands, that required conversion stations or gateways to communicate.

<span style="font-size: large;">Various info</span>

  * Mr. Cerf has wired his house with numerous sensors, measuring light, temperature, etc. He can use this data to optimize energy usage - turn heating off in certain areas before they reach their target temperature, etc.
  * He raised the question of persistence of information. Currently we're able to examine papyrus scrolls thousands of years old. However, it has become very difficult to read electronic data more than 20-30 years old. Humanity needs to find a way to preserve data in a format that is readable longer than half a generation.
  * His latest work concerns an Interplanetary Internet. This addresses the enormous lag times involved in communications between the planets. As to why we would need this, he describes how the Mars Rovers were sending data to Earth initially: through a slow, overheating long-range radio. By switching to a shorter range radio the Rovers were able to increase throughput, however, they couldn't communicate with Earth directly. The solution was to use the Mars Orbiters as relays, using a store-and-forward model. This resulted in a new Bundle Protocol, described in <a href="http://www.rfc-archive.org/getrfc.php?rfc=5050" target="_blank">RFC 5050</a>.

<div>
  The speech was scheduled for about 45 minutes, with 15 minutes for questions. The speech lasted much longer... but there was still time for a few questions. It was really interesting to see how Mr. Cerf, 66 years old, still keeps up with the latest developments, and can think on his feet faster than a lot of people I know.
</div>

<div>
</div>