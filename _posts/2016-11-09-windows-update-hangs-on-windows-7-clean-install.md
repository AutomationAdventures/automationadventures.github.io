---
title: 'Windows Update hangs on Windows 7 after clean install'
date: 2016-11-09T08:00:08-04:00
author: Ron
layout: post
categories:
  - Uncategorized
---
![Windows7](/wp-content/uploads/2016/11/Windows7.png)

Recently, I installed a fresh (pre-SP1) Windows 7 VM, and it didn't go very smoothly. After a few Windows Updates I got an update to Windows Update itself (yay!). Unfortunately, after that update was applied, all subsequent tries to run Windows Update and check for updates, resulted in "Searching for updates..." for hours, nay, days.

Several solutions were suggested online, ranging from purging the Windows Update temporary directory to installing a small WSUS server on a USB stick and using that instead of Microsoft Windows as an update source. I even tried to install Steve Gibson's [Never10](https://www.grc.com/never10.htm), since it contained a trigger warning for an outdated Windows Update. It did trigger, it installed an update, but the next Windows Update check resulted once again in a "Searching for updates". Bummer.

But the following solution found in [answers.microsoft.com](https://answers.microsoft.com/en-us/windows/forum/windows_7-update/windows-update-agent-767600320-destroys-windows/c870d7f0-9685-4847-b623-e11239ba80ea?page=4") worked like a charm:

1. Download [Microsoft KB3083710](https://support.microsoft.com/en-us/kb/3083710)
2. Download [Microsoft KB3102810](https://support.microsoft.com/en-us/kb/3102810)
3. Download Windows Update Diagnostics Tool in order to reset Windows Update ([support.microsoft.com/en-us/kb/971058](https://support.microsoft.com/en-us/kb/971058))
4. Restart Windows
5. Manually install KB3083710 (this results in a Windows reboot)
6. Manually install KB3102810 (this results in a Windows reboot)
7. Restart Windows manually (finalizing the installation of KB3102810 happens after the last reboot)
8. Run the Windows Update Diagnostics Tool
9. Restart computer again and search for updates

The search may take several minutes, so make sure to leave adequate time (I've seen times up to an hour mentioned in other forums). My VM is now happily downloading 229 updates, and is 52% complete.