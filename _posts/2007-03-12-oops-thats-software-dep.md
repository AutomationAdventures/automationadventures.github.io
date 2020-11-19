---
id: 303
title: 'Oops. That''s Software DEP...'
date: 2007-03-12T13:15:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=303
permalink: /2007/03/oops-thats-software-dep.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2007/03/oops-that-software-dep_12.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/7696993904287706632
categories:
  - Windows
---
I think I confused Hardware and Software DEP in [a recent post](/2007/03/how-to-stop-windows-vulnerabilities-before-they-are-known-with-dep.html). The description of turning on Data Execution Prevention in the Performance option is Software DEP, as described by [this Microsoft article](http://www.microsoft.com/technet/security/prodtech/windowsxp/depcnfxp.mspx).

Microsoft also has [an article about turning on Hardware DEP,](http://support.microsoft.com/kb/875352) which, as [Steve Gibson](http://www.grc.com/) said in Security Now #78, can result in a system not booting because some 3rd party driver causes a DEP violation. So be careful when following the instructions, or wait for Steve's DEPuty utility.