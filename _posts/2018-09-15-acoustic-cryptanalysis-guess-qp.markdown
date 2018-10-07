---
layout: post
title:  "Acoustic cryptanalysis: guess 'q' or 'p'"
date:   2018-09-15 13:00:00 +0200
htmlarr:
- guess-qp.html
categories: jekyll update
---

This post is about a very preliminary demo for a side channel attack using sounds emitted by the keyboard.  The goal is
to guess which key has been pressed based only on the emitted sound. Below is a simple program that tries to guess
whether the user pressed the **'q'** or the **'p'** key.

<h1>Algorithm</h1>

The program first asks the user to press the **'q'** and **'p'** keys several times in order to *train* itself how the
two keys sound. After the training is completed, the program continues to accept key presses, but now it tries to guess
the key using only the captured audio data. The predicted key is displayed on the screen.

For each key, we compute an average waveform using the audio data captured during the training stage. Then for a new
waveform, we compute the cross correlation (CC) with each of the known average waveforms (in this case just 2) and
predict that the pressed key is the one for which the CC is maximum.

To make things easier, there are several simplifications made:

<ul>
<li>
Around 1.0 second of audio is recorded around each key press, so make sure you type slowly.
</li>
<li>
Currently the program cannot calculate the moment of the key press, so it gets
this information from the keyboard (in the demo below - from the input HTML element). Ideally, we would like to
automatically detect the time of the key presses by analyzing just the audio.
</li>
</ul>

<h1>Some initial results</h1>

I have currently tested this program on two different keyboards - a mechanical one and a standard non-mechanical one.
When using the mechanical keyboard the accuracy of the predictions is very high (close to 100%). For the non-mechanical
keyboard - the results are much worse. My guess is that the mechanical keyboard emits much more distinguishable sounds
compared to the non-mechanical. Also, one might need to use a more sophisticated approach than the described one for the
case of non-mechanical keyboards.

<h1>Demo</h1>

Press the **Init** button to start. Make sure to allow audio capture on this page. Follow the instructions shown in the
*Standard output* window below.
