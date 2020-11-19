---
id: 308
title: Daylight Savings Time change on Ubuntu Linux
date: 2007-03-06T13:32:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=308
permalink: /2007/03/daylight-savings-time-change-on-ubuntu-linux.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/03/daylight-savings-time-change-on-ubuntu_06.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/2020337631035581018
categories:
  - Linux
---
This coming weekend is the first time the DST in the US starts on the second weekend in March, as opposed to the first weekend in April. This is due to the passing of the Energy Policy Act in 2005. So, likely, anything written before 2005 is going to be FUBAR'ed this weekend...

[Linux Watch](http://www.linux-watch.com/) has an [informative article](http://www.linux-watch.com/news/NS6300294422.html) about the workings of DST on Linux-based systems, and pointers to how the various distributions are handling the changed DST. Ubuntu is missing from that list, but any of the Debian packages (they both point to the same version of the tzdata package) should work.

To verify your system is ready for this weekend's time change, type in the following command:

`zdump -v /etc/localtime | grep 2007`

If all is well, the first two lines should contain a March 11th date. Here's the output of my system:

```
/etc/localtime Sun Mar 11 06:59:59 2007 UTC = Sun Mar 11 01:59:59 2007 EST isdst=0 gmtoff=-18000
/etc/localtime Sun Mar 11 07:00:00 2007 UTC = Sun Mar 11 03:00:00 2007 EDT isdst=1 gmtoff=-14400
/etc/localtime Sun Nov 4 05:59:59 2007 UTC = Sun Nov 4 01:59:59 2007 EDT isdst=1 gmtoff=-14400
/etc/localtime Sun Nov 4 06:00:00 2007 UTC = Sun Nov 4 01:00:00 2007 EST isdst=0 gmtoff=-18000
```

If your output doesn't contain the March 11th date, you need to run a standard update to make sure you have all the latest patches installed:

`sudo apt-get dist-upgrade`

Run the zdump command again. If it still doesn't show the March 11th date, you need to resort to the manual update described in the Linux Watch article, but the APT upgrade should take care of it.

Now get some rest. We're losing an hour sleep this weekend, but at least the Ubuntu systems will hum along quite nicely.