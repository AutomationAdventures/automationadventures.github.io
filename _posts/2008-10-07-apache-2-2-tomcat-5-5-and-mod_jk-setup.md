---
id: 193
title: Apache 2.2, Tomcat 5.5 and mod_jk setup
date: 2008-10-07T12:27:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=193
permalink: /2008/10/apache-2-2-tomcat-5-5-and-mod_jk-setup.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2008/10/apache-22-tomcat-55-and-modjk-setup.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/6902028547185962152
categories:
  - apache
  - java
  - mod_jk
  - Network
  - tomcat
  - webservice
---
I've begun to experiment with some web services at work, and an ex-colleague of mine had set up some instructions on how to configure Apache, Tomcat and mod-jk to seamlessly pass requests from Apache to Tomcat. However, the instructions were written a major version ago, and didn't quite work with Tomcat 5.5 and the latest mod_jk.

The main problem was the reference to ApacheConfig. In Tomcat 4 this was org.apache.ajp.tomcat4.config.ApacheConfig. No twiddling with it seemed to help, and Tomcat 5 kept giving load errors. This part was referencing how to have mod_jk and Apache automatically create a configuration file. The Apache website wasn't very helpful...

Finally, I came across a forum post somewhere (sorry, I forgot where), giving the answer: the Listener className should be org.apache.jk.config.ApacheConfig. After replacing that line in Tomcat's conf/server.xml file, everything seemed to work like a charm!