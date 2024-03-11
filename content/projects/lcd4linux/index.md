+++
title = 'lcd4linux System Monitor'
draft = false
date = 2024-02-09T05:28:24-04:00
layout = "projects"
summary = "Tinkering with lcd4linux on a cheap AX206 display."
+++
## Background
A while ago, I got this cool little AX206 display from AliExpress for about $20AUD. Adding in the internal USB 2.0 header to USB-C cable for another $3 or so, plus a USB header splitter (thanks to already having two RGB controllers for the two headers) for another $3, and that's a neat little screen on the inside of your PC.

### Back on Windows
Back when I used to use Windows, the screen just worked AIDA64 after installing a particular driver. (although, in retrospect, I feel that lcd4linux works much better! More on that later...)

## lcd4linux
### Thought it Was Broken?
I'd been wanting to try out lcd4linux for a long time, but I just couldn't get the package on the AUR to build for the life of me. I was getting some sort of `libusb` error, and I couldn't figure out what it was since I had `libusb` installed. Turns out, i was missing `libusb-compat`, which Arch has split off from the main package, and actually wasn't marked as a dependency to my knowledge.

### Learning the Config
At first, `lcd4linux.conf` seemed pretty confusing. I started off with one of [dpf-ax](https://github.com/dreamlayers/dpf-ax)'s premade configs, (the 320x240 config, which was too small for my 480x320 display). After a few hours of tinkering around, ~~stealing~~ getting inspiration from other peoples' *years old* configs (yeah, lcd4linux is kinda dead at this point, but hey, it still works and that's all that matters), I was able to finish with this config which I got adjusted just to my tastes.

### My Config
My config's got a bit of kernel information + local IP address scrolling through the top, as well as a CPU utilisation bar, CPU frequency bar (with average on all cores and highest core frequency sub-bars), as well as a RAM and network (up + down sub-bars) bar, and last but not least - an uptime counter right at the bottom. 

#### Github Repo
If you'd like to take a look at ~~or steal~~ my config, it's here on my Github Repo - [harija-lcd4linux-config-ax206](https://github.com/harrythezomby/harija-lcd4linux-config-ax206)

#### Image
![lcd4linux System Monitor](/img/pc/lcd4linux.png)