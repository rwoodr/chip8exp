&nbsp;  

# Coding experiments in Chip-8 and variants

I've been playing with
[Octo](https://johnearnest.github.io/Octo/index.html), a high-level assembler for the
[Chip-8](https://en.wikipedia.org/wiki/CHIP-8) virtual machine.
Chip-8 is an interpreted programming language from 1977, written for CDP1802 based computers.
Octo supports the original Chip-8 specifications as well as several expanded variants.
This repository is a collection of my Chip-8 coding experiments.  
&nbsp;  
&nbsp;  

## Bresenham's line algorithm

File: lines-bresenham.8o

This algorithm for plotting an approximation of a straight line on a grid was developed by Jack Bresenham in 1962.
The version presented here evolved from attempting to copy the example on
[Wikipedia](https://en.wikipedia.org/wiki/Bresenham%27s_line_algorithm).
My first working implementation was not pretty, so I dug a bit deeper. I found help in a
[post by BESQUEUT](https://picaxeforum.co.uk/threads/converting-bresenhams-line-plotting-algorithm.29536/),
who modified a version posted by AllyCat, whose version was ported from the BBC Basic version on
[Rosetta Code](https://rosettacode.org/wiki/Bitmap/Bresenham%27s_line_algorithm#BBC_BASIC).


This gif example of random lines is using the `hires` 128x64 mode of SCHIP and running in Octo at the lowest speed of 7 cycles/frame.

![GIF recording of Bresenham's line algorithm in Octo](/images/lines-bresenham.gif)


