---
id: 262
title: Windows Powershell 1.0
date: 2007-11-20T18:16:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=262
permalink: /2007/11/windows-powershell-1-0.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/11/windows-powershell-10.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/7674475632055802854
categories:
  - powershell
  - print
  - search
  - utility
  - Windows
---
Today I ran into an interesting problem. I wanted to print out a search result set - I needed to check off some of the files that I found from a Windows Search result, and add the ones that weren't checked off to another list. Apparently, the only option in Windows is to make screen shots and paste them into Word to print them. If you have more than two or three screens, that can become a drag.

There had to be a better method. Our systems guy suggested using Posix tools for Windows, and then using ls or find to get to the right data. I didn't feel like adding yet another non-Microsoft utility (that will become unsupported in no time) to the mix of things. Then I remembered looking at [PowerShell](http://www.microsoft.com/windowsserver2003/technologies/management/powershell/default.mspx) a couple of months ago.

PowerShell is the next generation command line for Windows. It approaches everything in the system as an object, and you can perform operations on those objects, retrieve information from them, etc. When I looked at it, my reaction was "Cool!", but since I didn't have an actual need for it, it dwindled away in a corner of the harddisk, until I needed disk space and it was deleted.

Basically, what I needed to do was select all the files in a certain directory, and all its subdirectories, with a certain file extension (*.r, for compiled Progress code), that were created after October 24th. Of those files, I need to know the filename, and path.

After some fiddling around, and realizing that I needed the last written date instead of the creation date, I came up with the following beauty:

> Get-ChildItem -filter *.r -recurse | where { $_.LastWriteTime -gt "10/24/2007" } | Format-List FullName | Out-Printer

I would have preferred Format-Table, but it turned out some of the paths were too long to be displayed in the table list.

PowerShell 1.0 looks pretty promising, and [PowerShell 2.0](http://www.microsoft.com/downloads/details.aspx?FamilyID=60deac2b-975b-41e6-9fa0-c2fd6aa6bc89&displaylang=en) is currently in beta, looking even better. This may be something that will be in my standard toolbox from now on.