---
id: 179
title: 'ICVerify: encrypt request and answer files using EncryptionManager'
date: 2009-02-13T13:16:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=179
permalink: /2009/02/icverify-encrypt-request-and-answer-files-using-encryptionmanager.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/02/icverify-encrypt-request-and-answer.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/58320650300381014
categories:
  - 4gl
  - answer
  - encryption
  - encryptionmanager.dll
  - icverify
  - progress
  - request
---
To increase the security when dealing with credit card processing via ICVerify's request/answer methodology, it is possible to encrypt and decrypt this information. However, the documentation is fairly sketchy on this subject, especially when you're not working in one of the languages used in the examples in the SDK.

After some hair-pulling on why it doesn't work, I think I've got it figured out now. Here are the steps I used to get it working:

  1. EncryptionManager.DLL is not a normal DLL, it is a .NET assembly. Trying to register it with regsrv32 will result in an error message, saying that it doesn't have a DLLRegisterServer entry point. The trick is to use either the .NET gacutl.exe or the icvgacutil.exe supplied on the ICVerify SDK CD.  
    **UPDATE:**You also have to use regasm to register the assembly!
  2. Once registered at the Global Assembly Cache (GAC), the name of the DLL is not EncryptionManager. To make things more interesting, I had to link to the name _FirstData.Encryption.Facade.EncryptionManager_. The only way to figure this out is to dig through the registry after registering the DLL, or to use the option on the GAC utility to write out a registry modification file.
  3. In Progress, you can use the COM viewer to access EncryptionManager.tlb, and see the different methods defined in the DLL. You're only going to be using 2 of them most likely: _EncryptThirdPartyMessage_ and _DecryptThirdPartyMessage_. Both use the creation date of the file you're working with, so be careful not to copy this file or move it across file systems.

<div>
  The Progress code I used to encrypt a request file is as follows:
</div>

> DEFINE VARIABLE vhEncryption AS COM-HANDLE NO-UNDO.  
> DEFINE VARIABLE vcPrepFilename AS CHARACTER NO-UNDO
> 
> <div style="padding-left: 30px;">
>   INITIAL "C:TEMPicver001.prep".
> </div>
> 
> DEFINE VARIABLE vcReqFilename AS CHARACTER NO-UNDO
> 
> <div style="padding-left: 30px;">
>   INITIAL "C:TEMPicver001.req".
> </div>
> 
> DEFINE VARIABLE vcEncrypted AS CHARACTER NO-UNDO.  
> DEFINE VARIABLE vcRequest AS CHARACTER NO-UNDO.  
> DEFINE STREAM sOutput.
> 
> UPDATE vcRequest FORMAT "x(60)".  
> CREATE "FirstData.Encryption.Facade.EncryptionManager" vhEncryption.  
> OUTPUT STREAM sOutput TO VALUE(vcPrepFilename).  
> vcEncrypted = vhEncryption:EncryptThirdPartyMessage(vcPrepFilename,vcRequest).  
> PUT STREAM sOutput UNFORMATTED vcEncrypted.  
> OUTPUT STREAM sOutput CLOSE.  
> OS-RENAME VALUE(vcPrepFilename) VALUE(vcReqFilename).

The decryption routine is somewhat simpler, since we don't have to move files around so much:

> DEFINE VARIABLE vhEncryption     AS COM-HANDLE NO-UNDO.  
> DEFINE VARIABLE vcAnswerFilename AS CHARACTER NO-UNDO
> 
> <div style="padding-left: 30px;">
>   INITIAL "C:TEMPicver001.ans".
> </div>
> 
> DEFINE VARIABLE vcEncrypted AS CHARACTER NO-UNDO.  
> DEFINE VARIABLE vcDecrypted AS CHARACTER NO-UNDO.  
> DEFINE STREAM sInput.
> 
> CREATE "FirstData.Encryption.Facade.EncryptionManager" vhEncryption.  
> INPUT STREAM sInput FROM VALUE(vcAnswerFilename).  
> IMPORT STREAM sInput UNFORMATTED vcEncrypted.  
> vcDecrypted = vhEncryption:DecryptThirdPartyMessage(vcAnswerFilename,vcEncrypted).  
> INPUT STREAM sInput CLOSE.

These code snippets should have some more error checking. Also, the request can be more than one line, depending on the version of ICVerify and the answer file settings in the configuration.