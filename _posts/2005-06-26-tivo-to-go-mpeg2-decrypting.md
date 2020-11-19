---
id: 367
title: TiVo To Go MPEG2 Decrypting
date: 2005-06-26T12:28:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=367
permalink: /2005/06/tivo-to-go-mpeg2-decrypting.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2005/06/tivo-to-go-mpeg2-decrypting_26.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/4371724528741561192
categories:
  - PVR
---
OK, this is more a personal note:

While going through my stack of papers that accumulated on my desk, I came across this printout, referring to a page on www.evillabs.net/tivo, describing how to remove MPEG2 encrypting. This may come in handy when I want to do some editing on Linux, so just for the sake of posterity:

[BEGIN QUOTE]

FOR PERSONAL USE ONLY! DO NOT REDISTRIBUTE THESE MPEG2 STREAM OUTSIDE OF YOUR HOUSEHOLD!

Preparatory Steps  
You will need the DirectShow GraphEdit.exe (available in the Microsoft DirectX 9.0 SDK, or Google it), and the following DirectShow Filters:

  * TiVo DirectShow Filter Source
  * MPEG2 Demuxer (Moonlight/Elecard recommended)
  * MPEG2 Multiplexer (Moonlight M71 recommended)  
    (You can get both of these from the XMuxer Pro evaluation version)
  * Dump (available in the DirectX 9.0SDK)  
    (You can get both graphedit and dump.ax from this guy)

Now what?

  1. Open up GraphEdit.exe
  2. Drag you SomeVideo.tivo into the GraphEdit work area
  3. Delete (select and press Delete) everything but the source box (the one with your video's filename in it)
  4. Select Graph / Insert Filter... / DirectShow Filters
  5. Dig around for a MPEG2 Demuxer
  6. Add it to the graph, and draw a line from the source file's output pin to the demuxer's input pin
  7. Dig around for a MPEG2 Muxer and add it to the graph.
  8. Draw a line from the demuxer's video output pins to the muxer's input pin. Do the same for the audio output pin of the demuxer.
  9. Dig around for Dump.
 10. Add it to the graph (selecting an output file, i.e. "dump3.mpeg") and tie the muxer's output pin.
 11. Your graph should look something like this: 
      * Your Tivo file with an output connector
      * A connection from your TiVo file to the MPEG2 Demux
      * An MPEG2 Demultiplexer with one input connector, and two output connectors (video and audio)
      * Two connections (audio and video) between the Demuxer outputs and the Muxer inputs
      * An MPEG2 Muxer with two inputs and one output connector
      * A connection from the Muxer output to the dump input
      * An output file with one input
 12. Press "Play" on the GraphEdit toolbar, and, in under 5 minutes, you have an unencrypted MPEG2 streem. Joy!

[END QUOTE]

Now this document is a semi-perfect copy of the one that used to be up on evillabs (I can't reach the website right now), and you should only use it for personal use.