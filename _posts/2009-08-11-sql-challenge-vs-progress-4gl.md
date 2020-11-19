---
id: 166
title: SQL Challenge vs. Progress 4GL
date: 2009-08-11T11:40:00-04:00
author: Ron
layout: post
guid: http://blog-autadv.rhcloud.com/?p=166
permalink: /2009/08/sql-challenge-vs-progress-4gl.html
blogger_blog:
  - www.automationadventures.com
blogger_author:
  - Ronald Bruintjes
blogger_permalink:
  - /2009/08/sql-challenge-vs-progress-4gl.html
blogger_internal:
  - /feeds/8074648837853537542/posts/default/8764207668073483120
categories:
  - 4gl
  - challenge
  - code
  - Miscellaneous
  - programming
  - progress
  - sql
---
One of the newsletters I subscribe to is the [SQLCentral solutions](http://www.sqlservercentral.com/). A couple of weeks ago they issued the [Summer SQL Stumpers 2009](http://www.sqlservercentral.com/articles/T-SQL/67666/), asking for the fastest way to calculate all the primes 1000 or lower. The fastest solution they came up with runs in about 7 seconds, which I thought was terribly slow for the algorithm used (Sieve of Atkins and Aristophanes), and I thought I'd give Progress a try. I came up with the following:

```
DEFINE TEMP-TABLE ttPrime
FIELD prime AS INTEGER
INDEX prime prime.
DEFINE VARIABLE i AS INTEGER     NO-UNDO.
DEFINE VARIABLE test-val AS INTEGER     NO-UNDO.

ETIME(TRUE).

DO i = 1 TO 1000:
  CREATE ttPrime.
  ASSIGN
    ttPrime.prime = i.
END.

DO i = 2 TO 499:
  ASSIGN test-val = i * 2.
  REPEAT WHILE test-val < = 1000:
    FOR FIRST ttPrime
      WHERE ttPrime.prime = test-val
      EXCLUSIVE-LOCK:
      DELETE ttPrime.
    END.
    ASSIGN test-val = test-val + i.
  END.
END.

MESSAGE "Etime" ETIME
  VIEW-AS ALERT-BOX INFO.

FOR EACH ttPrime
  NO-LOCK:
  DISPLAY ttPrime.
END.
```

On my machine the procedure runs in about 93 milliseconds, and as far as I can see the results are accurate. Progress 4GL FTW!