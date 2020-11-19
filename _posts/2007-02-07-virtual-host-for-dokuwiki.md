---
id: 313
title: Virtual Host for DokuWiki
date: 2007-02-07T11:45:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=313
permalink: /2007/02/virtual-host-for-dokuwiki.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/02/virtual-host-for-dokuwiki.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/5806808199210495910
categories:
  - Linux
  - Network
---
As I mentioned [before](/2007/01/ubuntu-606-lamp-server-install.html), we've set up an Ubuntu server with Apache, MySQL, and PHP, to run, amongst other things, a wiki (in our case DokuWiki). For some reason the main page was working fine, but any other pages were showing up as var\_www\_vhosts\_wiki.medeco.com\_whatever.

After some frustrating searches around the Web, I finally figured out what I did wrong. Here are the steps I took:

1. Set up Virtual Hosts in Apache:
2. Create the directory for your virtual domain under the vhosts directory
3. Create a file in /etc/apache2/sites-available with the same name as your virtual domain, containing the following:
```
    <VirtualHost wiki.medeco.com>
      ServerName wiki.medeco.com
      ServerAlias wiki
      DocumentRoot /var/www/vhosts/wiki.medeco.com/web
      ErrorLog /var/log/apache2/wiki-error.log
      CustomLog /var/log/apache2/wiki-access.log common
      RewriteLog /var/log/apache2/wiki-rewrite.log
      <Directory /var/www/vhosts/wiki.medeco.com/web>
        Options -Indexes +FollowSymLinks
        Order allow,deny
        Allow from all
        RewriteEngine on
        RewriteRule ^_media/(.*) lib/exe/fetch.php?media=$1 [QSA,L]
        RewriteRule ^_detail/(.*) lib/exe/detail.php?media=$1 [QSA,L]
        RewriteRule ^$ doku.php [L]
        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteCond %{REQUEST_FILENAME} !-d
        RewriteRule (.*) doku.php?id=$1 [QSA,L]
      </Directory>
    </VirtualHost>
  ```
  4. Create a symbolic link in /etc/apache2/sites-enabled, pointing to your virtual domain config file in sites-available:  
    `ln -s /etc/apache2/sites-available/wiki.medeco.com /etc/apache2/sites-enables/001-wiki.medeco.com`
  5. Touch your local DokuWiki config file:  
    `sudo touch /var/www/vhosts/wiki.medeco.com/web/conf/local.php`
  6. Restart Apache by entering  
    `sudo /etc/init.d/apache2 restart`