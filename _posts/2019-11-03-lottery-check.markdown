---
layout: post
title:  "Could I have won the lottery?"
date:   2019-11-03 10:00:00 +0200
htmlarr:
- toto-check.html
categories: jekyll update
---

I was wondering what would have happened if I persistently played my favorite
6 numbers in the Bulgarian "6 out of 49" lottery - did I ever had the chance
to win the big jackpot and simply missed it by not playing?

The short answer is - "No", but in case you were wondering the same thing, you
can now easily check. Enter any 6 numbers in the grid below and
see if they were ever played. The archive contains data starting from 1958 until
today (the data is from the [official lottery site](http://www.toto.bg/statistika/6x49)).

**Note:** *this page opens a web-socket connection to a [remote server of mine](http://85.90.246.132:5003)
in order to fetch an up-to-date lottery archive. Unfortunately, I'm too lazy
to deal with SSL ceritificates, so currently the connection is over non-secure
web-sockets. This triggers "content blocked" browser warnings - sorry :(*

[Source code](https://github.com/ggerganov/toto-check)
