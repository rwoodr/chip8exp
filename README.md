&nbsp;  

# Coding experiments in Chip-8

I've been experimenting with Chip-8 and SCHIP using
[Octo](https://johnearnest.github.io/Octo/index.html), a high-level assembler for the
[Chip-8](https://en.wikipedia.org/wiki/CHIP-8) virtual machine.
Chip-8 is an interpreted programming language from 1977, written for CDP1802 based computers.
Octo supports the original Chip-8 specifications as well as several expanded variants.
This repository is a collection of my Octo coding experiments.  
&nbsp;  
&nbsp;  

## Bresenham's line algorithm

Source: [lines-bresenham.8o](./lines-bresenham.8o) ([open in Octo](https://johnearnest.github.io/Octo/index.html?key=Pwickczd))

Bresenham's algorithm for plotting an approximation of a straight line on a grid was developed by Jack Bresenham in 1962.
The version presented here evolved from attempting to translate the example on
[Wikipedia](https://en.wikipedia.org/wiki/Bresenham%27s_line_algorithm).
My first working implementation was not pretty, so I dug deeper and found help in a
[forum post](https://picaxeforum.co.uk/threads/converting-bresenhams-line-plotting-algorithm.29536/).
The user BESQUEUT modified a version posted by AllyCat, whose version was ported from the BBC Basic version on
[Rosetta Code](https://rosettacode.org/wiki/Bitmap/Bresenham%27s_line_algorithm#BBC_BASIC).  
&nbsp;  

![GIF recording of Bresenham's line algorithm in Octo](./images/lines-bresenham.gif)  
Example of random lines using `hires` 128x64 mode of SCHIP and running in Octo  
at the lowest speed of 7 cycles/frame.  
&nbsp;  
&nbsp;  

## Optimized straight line algorithm

Source: [lines-straight.8o](./lines-straight.8o) ([open in Octo](https://johnearnest.github.io/Octo/index.html?key=tWmzzlTP))

This is is an optimized algorithm to draw horizontal and vertical lines from a start point and end point.
The algorithm draws the line left-to-right or top-to-bottom only, using as many 8-pixel segments as possible and then draws any
remaining portion of the line with a final 1 to 7 pixel segment. The code uses unrolled loops for increased performance, but a loop can
be used to save space. The vertical function uses self modifying code to set the sprite height of the final segment.  
&nbsp;  

![GIF recording of optimized straight line algorithm in Octo](./images/lines-straight.gif)  
Drawing random lines alternating between horizontal and vertical. Example uses  
SCHIP `hires` 128x64 mode running in Octo at the lowest speed of 7 cycles/frame.