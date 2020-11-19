---
id: 266
title: Setting up MXP to run under Linux
date: 2007-11-13T15:18:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=266
permalink: /2007/11/setting-up-mxp-to-run-under-linux.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/11/setting-up-mxp-to-run-under-linux.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/3503166714581954222
image: /wp-content/uploads/2007/11/MXP-in-Linux-672x372.png
categories:
  - fontforge
  - fonts
  - foresight
  - ies4linux
  - Linux
  - mxp
  - progress
  - ubuntu
  - Windows
  - wine
---
Recently our systems administrator asked me if it was possible to run <a href="http://www.foresightsw.com/" target="_blank">MXP </a>under Linux. "I don't think there is a client of Progress for Linux, at least not graphical", was my first response. But I got intrigued, and started digging (or rather, googling) around. And it is possible.

I'll describe what I did under <a href="http://www.ubuntu.com/" target="_blank">Ubuntu </a>7.10 with <a href="http://www.progress.com/openedge/index.ssp" target="_blank">Progress </a>10.0B, and <a href="http://www.foresightsw.com/" target="_blank">MXP </a>8.1E. The steps should be very similar for other Linux flavors, or later versions of Progress and MXP.  
<a name='more'></a>

## Step 1: Install Wine

The first step is the easiest: install <a href="http://www.winehq.org/" target="_blank">wine</a>.

> sudo apt-get install wine

This should install wine (if it wasn't already installed), and any dependencies.

## Step 2: Configure wine with IEs4Linux

The next step is to configure wine. You can do all of it manually, but by far the easiest is to use IEs4Linux. You don't have to use the latest beta (which includes support for IE7), since we're only interested in the underlying framework, not the support of IE.

The best place to look is the <a href="http://www.tatanka.com.br/ies4linux/page/Main_Page" target="_blank">IEs4Linux </a>website, but in case the steps aren't available:

  1. Open a terminal
  2. Open /etc/apt/sources.list  
        sudo gedit /etc/apt/sources.list
  3. Uncomment or add the following lines  
        deb http://us.archive.ubuntu.com/ubuntu gutsy universe
  4. Add this line:  
        deb http://wine.budgetdedicated.com/apt gutsy main
  5. Close gedit, update apt-get package list and install cabextract:  
        sudo apt-get update  
        sudo apt-get install cabextract  
    You might get an error about an untrusted site (wine.budgetdedicated.com), but you can ignore that.
  6. Download IEs4Linux and install  
        wget http://www.tatanka.com.br/ies4linux/downloads/ies4linux-latest.tar.gz  
        tar zxvf ies4linux-latest.tar.gz  
        cd ies4linux-*  
        ./ies4linux

## Step 3: Install Progress 10.0B

To install <a href="http://www.progress.com/openedge/index.ssp" target="_blank">Progress</a>, you have to have your license code handy. Also, in my case I had the installation CD copied to the hard drive. In any case, it's as easy as typing

> wine setup.exe

and following the prompts.

Note: the standard installation of wine treats everything as Windows 2000. I ran the setup under Windows 2000, then switched to Windows XP as standard. I don't think there is a difference for Progress.

## <big>Step 4: Installing MXP</big>

I'm assuming that you already have an installation of <a href="http://www.foresightsw.com/" target="_blank">MXP </a>on your network somewhere. If not, install it from a regular Windows machine, and copy your settings over.  
The installation of MXP hinges on a couple of things:

  1. The startup icon. Copy this from a Windows machine already running MXP
  2. The services file. This is used to connect to the proper databases. Add the services needed to /etc/services.
  3. Most installations have a shared drive that contains sources or compiled programs. So that will be our next step.

## Step 5: Creating a mount to a Windows Share

We have all the compiled programs installed on a share on our Windows server, which is mapped to the Q drive. The first step is to make this Windows share visible on our Linux box:

  1. Make sure you have the <a href="https://help.ubuntu.com/community/SettingUpSamba" target="_blank">Samba filesystem installed</a>:  
        sudo apt-get install smbfs 
  2. Add a line to /etc/fstab like this:  
        //admin/progress.mxp /mnt/progress.mxp smbfs credentials=/home/ronald/.smbpassword,user,defaults 0 0  
    This will allow the system to automatically mount the Windows share (//admin/progress.mxp) on a mounting point on Linux (/mnt/progress.mxp) as Samba (smbfs) with the credentials from a hidden file .smbpassword
  3. Create the .smbpassword file:  
        gedit .smbpassword  
        username=DOMAINronald  
        password=TopSecret

<div>
  You can get fancy by not automatically mounting the share during system startup, but adding an entry to your login script that mounts the drive properly. Let me know how that turns out... 🙂
</div>

## Step 6: Linking a drive letter to a Windows Share

Wine has a nice little solution to map shares to drive letters:

  1. Select Applications->Wine->Configure Wine
  2. Select the Drives tab
  3. Add a drive mapping

<div>
  The drive mapping will be the next available drive letter. If you're not happy with that, open a terminal, navigate to .wine/dosdevices, and create a symbolic link to the desired mounting point:
</div>

> ln -s /mnt/progress.mxp q:

## Step 7: Install the foresight.fon font

At this point you should be able to start MXP with the icon, and be OK until you actually enter a username and password. After that, all hell breaks lose because the foresight font is not installed properly. I muddled around for a while, and finally came across this:

  1. Make sure you have the <a href="http://corefonts.sourceforge.net/" target="_blank">microsoft core fonts</a> installed.  
        sudo apt-get install msttcorefonts 
  2. Install <a href="http://fontforge.sourceforge.net/" target="_blank">fontforge</a>  
        sudo apt-get install fontforge
  3. Use fontforge to convert foresight.fon to a BCF file.
  1. Open foresight.fon in fontforge.
  2. Go to the "Element" menu, and choose "Font Info..."
  3. Go to the Encoding tab
  4. Click the box next to Encoding (probably reads Windows Latin ("ANSI")
  5. Choose "ISO 8859-1 (Latin1)"
  6. Click "OK"
  7. Go to the File menu, choose "Generate Fonts..."
  8. The right hand box should be set to BDF, if not, change it to BDF
  9. Click "Save"
 10. 96 dpi is sufficient, click OK
 11. Go to where you saved the font, and rename it to how you want it to show up, i.e. foresight.bdf

  4. Convert it from BDF to PCF format:  
        bdftopcf -o foresight.pcf foresight.bdf
  5. Create a bitmapped fonts directory  
        sudo mkdir /usr/share/fonts/bitmaps
  6. Copy and install the font
  1. sudo cp foresight.pcf /usr/share/fonts/bitmaps
  2. sudo mkfontdir /usr/share/fonts/bitmaps

  7. Make the new directory available as a font directory  
        xset fp+ /usr/share/fonts/bitmaps
  8. Refresh the font server  
        sudo xset fp rehash

<div>
  The font should now be available, and MXP shouldn't complain about weird geometry anymore.
</div>

![MXP under Linux](/wp-content/uploads/2007/11/MXP-in-Linux.png)

