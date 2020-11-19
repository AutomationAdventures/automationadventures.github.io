---
id: 171
title: 'Tomcat uses 100% of CPU'
date: 2009-03-30T11:35:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=171
permalink: /2009/03/tomcat-uses-100-of-cpu.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/03/tomcat-uses-100-of-cpu.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/2711445621568627996
categories:
  - ajp
  - apache
  - cpu
  - Network
  - tomcat
  - usage
  - webservice
  - Windows
---
As I posted last week, I installed <a href="http://www.nagios.org/" target="_blank">Nagios </a>and the monitoring clients on a couple of machines. One of the machines I started monitoring was the machine we use to provide some internal webservices access to Progress databases. And this machine turned out to have a problem: 100% CPU usage!

Further investigation narrowed this down to TomCat using 99-100% capacity (basically anything it can get!). I've only seen this once before, with Microsoft Access, but since TomCat isn't a Microsoft product, I assumed there was something wrong with my setup. A little bit of digging revealed two possible solutions:

  1. There's a bug in the Java engine. Apparently there is a <a href="http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=4724129" target="_blank">Memory leak in the use of StringBuffer.toString()</a> in version 1.4.1, and fixed in version 1.4.1_05. This bug was submitted way back in 2002, so I assume if I download a new version of Java I should be OK. And since I'm running a 1.6 version, I don't think this is the issue.
  2. The AJP connector is misbehaving. I found a post (unfortunately can't remember where...) pointing to this connector as the culprit, and the solution was to explicitly state some of the default values for the parameters, with the exception of the connectionTimeout parameter. Instead of stating the obvious to TomCat, I decided to modify server.xml, and modify the AJP connector just enough so that it knows the connectionTimeout is 5000ms instead of eternity.  
    > <Connector port="8009"  
    > enableLookups="false" redirectPort="8443" protocol="AJP/1.3"  
    > connectionTimeout="5000"  
    > />

After implementing that last solution, the CPU usage for the machine dropped from 100% to about 9%.