+++
title = 'RAM Issues'
draft = false
date = 2024-09-20T06:29:28-04:00
summary = "Talking about getting RAM with mixed controllers stable."
tags = ["RAM", "PC"]
+++
## Introduction
So, turns out combining two sets of RAM (despite being the same marketed model) using the XMP profile of one is a bad idea. For a while, I'd been using an unstable RAM OC on my PC without too much issue ultimately, apart from when my Windows VM began randomly restarting at times, leading me to immediately suspect the mismatched RAM. After this, I decided to run `memtest86+`, and whaddaya know, I got a fail after not too long.

## Grrr... Corsair RAM
Now, I wasn't really sure why the default OC of two sets of RAM with the same exact frequency and timings (although of different capacities) wouldn't work well together, till I learnt that Corsair packages a plethora of different memory controllers into various sets of ram marketed under the same name/model. After some research, I learnt that my 32GB of Vengenace RGB SL had a Samsung E-Die, whereas my 16GB kit had a Nanya die (I forgot which one). Realising this mismatch, the whole issue of instability made sense, although I won't be buying Corsair RAM ever again because of this annoying practice making you have to rely on the version number on the actual ram heat-spreader, rather than the SKU on the box to determine what you actually got.
![Image (Cbb lol)](/img/ram/ramsticks.jpg)

## Messing With Settings
After a bunch of messing around with frequency and timings to get the best possible stable results without too much of a drop in speed and latency, I finally managed to get a stable few passes going for nearly 2 days using 3200mhz and the standard XMP timings of both sets, although with the CAS latency set to CL16 thanks to the drop in frequency. Also, I had to have the voltage set to 1.40V to achieve full stability, which was a little above the stock 1.35V, but ultimately shouldn't be too much of a problem, since many people believe these controllers can take up to 1.45V for 24/7 operation.
![Image (Cbb lol)](/img/ram/failon3600.jpg)
![Image (Cbb lol)](/img/ram/passon3200.jpg)

## Conclusion
Ultimately, this experience had me learn a lot about RAM, memory controllers, and what companies to definitely avoid for RAM, at least in the DDR4-era :p.

Thanks for reading!