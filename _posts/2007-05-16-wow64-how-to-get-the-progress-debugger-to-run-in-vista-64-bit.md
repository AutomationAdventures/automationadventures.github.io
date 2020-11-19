---
id: 292
title: 'Wow64: How to get the Progress Debugger to run in Vista 64-bit'
date: 2007-05-16T12:51:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=292
permalink: /2007/05/wow64-how-to-get-the-progress-debugger-to-run-in-vista-64-bit.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/05/wow64-how-to-get-progress-debugger-to.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/5957639687632897524
categories:
  - Windows
---
Well, I just spent close to two days figuring out how to make the Progress Debugger to run in Windows Vista 64-bit.

When we first installed OpenEdge 10.0B on Vista, an error message popped up that the registry key HKEY_LOCAL_MACHINE\SOFTWARE\Secure couldn't be accessed. Since everything seemed to work OK, we didn't pay much attention to it.

Until we tried to debug a program, and Progress informed us that we had to enable debugging. prodebugenable seems to do little more than change the value of HKEY_LOCAL_MACHINE\SOFTWARE\Secure\ProDbgCK\"C:\DLC100B" from "Debugging disabled" to "Debugging enabled". A co-worker of mine, running Windows Vista 32-bit, simply pulled up the registry editor, and created the necessary keys.

When I did that in the 64-bit version, prodebugenable still complained it couldn't access the registry key HKLMSoftwareSecure. Suspecting a rights issue, I installed a utility called subinacl, that allows to read and change the rights on registry keys. However, this utility also couldn't find the registry key... and it's a 32-bit program. Hmm.

It turns out that Vista employs a virtualization of the registry for 32-bit programs. There is a node called HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node, under which 32-bit programs can create keys. It's still a little black magic for me, but here are the steps I took to create the necessary keys and get the Progress Debugger to work:

1. Open a command shell, running as Administrator: find the cmd command, right-click on it, and select "Run as administrator"
2. Type the command  
`reg add HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node /v Secure`
3. Type the command  
`reg add HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Secure /v ProDbgCK`
4. Type the command  
`reg add HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Secure\ProDbgCK /v "C:\DLC100B.state" /d "Debugging disabled"`
5. Verify the correctness of the keys by typing the command  
`reg query HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Secure\ProDbgCK`
6. It should show you the state key with the value "Debugging disabled".
7. Now open the Proenv environment, also running as Administrator.
8. Type the command  
`prodebugenable -enable-all`
9. You should get the confirmation that debugging is now enabled.

After these steps, you can start using the debugger. If these steps don't work, I'd be interested in hearing from you.

One drawback: if you're running Aero in Vista, activating the debugger switches the theme to Windows Classic. It doesn't switch back automatically...

<strong>Update 2/15/2019</strong>

I went through this article today, while installing Progress 10.0B05 under Windows 10 64-bit. A lot of the same problems, but when I tried to install SP5, I got a new error: "OpenEdge r10.0 installation corrupted: "DLC" registry key not found". Several Progress KB articles address this issue, but only one gave a solution that worked:
   
    Manually add the DLC string containing the path to the Progress OpenEdge install directory (%DLC%) to the Startup registry key:

    For 32-bit OpenEdge installs on 32-bit Windows Servers / 64-bit OpenEdge installs on 64-bit Windows Servers:
    
    HKEY_LOCAL_MACHINE\SOFTWARE\PSC\PROGRESS\<version>\Startup

    For 32-bit OpenEdge installs on 64-bit Windows Servers:

    HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\PSC\PROGRESS\<version>\Startup
    
1. Start REGEDIT from the RUN command then navigate to the appropriate Startup registry key.
2. With the mouse on the Startup key press right mouse key and select New -> String Value.
3. Create a String value and call it DLC.
4. Then set the Value name: DLC and the Value data: (should be the path of the OpenEdge installation).
```
Example:
Value name: DLC
Value data: C:\Progress\OpenEdge
```
5. Exit regedit.
6. Run setup.exe again to install the Service Pack.

After applying this registry key, the SP5 update went through and I now have a OpenEdge 10.0B05 version running on Windows 10.
