---
layout: post
title:  "Data over sound in the browser: Part 2"
date:   2018-05-31 18:00:00 +0200
htmlarr:
- wave-text.html
categories: jekyll update
---

The transmission reliability in my [previous post]({% post_url 2018-02-11-wave-em %}) has not been very satisfying.
Moreover, looking at available data-over-sound implementations on the internet, I haven't found anything that really
works. Below is an attempt to make a reliable transmission, even when the devices are far from each other and the
environment is noisy.

This post provides a tool for broadcasting short messages (max 140 characters) over sound. The implementation is a
modified version of the [wave-share]({% post_url 2018-04-14-wave-share %}) algorithm, providing support for variable
data length. My personal experience is that this type of transmission is very robust to surrounding noise. Devices can
communicate easily within the same room (~4-5 meters distance). The transfer speed is around 8-16 B/s depending on the
selected Tx protocol.
