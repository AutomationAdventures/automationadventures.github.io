---
id: 147
title: Ubuntu and the Symantec Backup client
date: 2010-01-05T12:30:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=147
permalink: /2010/01/ubuntu-and-the-symantec-backup-client.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2010/01/ubuntu-and-symantec-backup-client.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/1887319151456246713
categories:
  - backup
  - backup exec
  - Linux
  - localhost
  - Network
  - symantec
  - ubuntu
---
At our company we're using Symantec Backup Exec to back up all our servers, including some Linux machines. I set up a newer Ubuntu install (9.04) on VMWare, and was pretty confident I would be able to get the backup working (using the Legacy agent). Well, that was not as easy as it seemed...

I followed the <a href="http://seer.entsupport.symantec.com/docs/240654.htm" target="_blank">instructions</a> on installing the legacy agent. After some tweaking here and there, the server was now showing up in the list of legacy agents on the Backup Exec server. However, every time I tried to pull up information on the server, Backup Exec returned an error, saying the server refused connections and may be running out of available network connections. Nonsense. But something was not right apparently.

Googling around for instructions, and suspecting a firewall or security setting, I tried tweaking access to the ports Backup Exec is using. No effect. Then I hit upon something: luckily I had an older Ubuntu server running with the legacy Backup Exec client, and could compare settings. It turns out that Ubuntu installs a host file with the following content:

> 127.0.0.1 localhost  
> 127.0.1.1 fqdn.domain.com fqdn

Why is there a difference in the third tuple? On the older server, both lines referred to 127.0.0.1. I decided to change the 2nd line on the newer server to 127.0.0.1 and reboot. After giving everything some time to publicize itself on the network, it appeared and asked for the credentials to use for the new server. I selected the correct user, and to my astonishment, the complete directory structure appeared.

I don't know why there are two different entries for the local machine, but it definitely broke the legacy Backup Exec client. Now I can only hope I never have use our backups...!