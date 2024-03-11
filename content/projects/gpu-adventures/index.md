+++
title = 'GPU Adventures For VFIO'
draft = false
date = 2024-02-10T06:28:24-04:00
layout = "projects"
summary = "My adventure of trying out two Intel Arc Cards on my host on both a B450 and X570 motherboard."
+++
## Background
So I'd been wanting to try out GPU Passthrough on my PC, having tried it out on my [Laptop](/posts/gpu-passthrough/). I'm honestly not much of a masochist so I never bothered with Single GPU PT, instead opting to pick up a second GPU and go all out.

## First Card - Sparkle Arc A380
### Looked Decent...
I began by picking up a Sparkle Arc A380, since it was fairly cheap new (about $200AUD), wouldn't be pushing my 750W PSU too hard, and had three Displayports (which was my main requirement so I could drive all three of my monitors). 

### Unboxing
Unboxing was pretty uneventful, the box was not the best but not the worst. (The A750 LE's box was miles better and a way more fun unboxing experience imo). Here's a picture of the box:
![A380 Box](/img/pc/a380box.png)

### Gallery
As you can see, the Sparkle is tiny... Making the 2070 Super seem like a beast:
![A380 Side by Side](/img/pc/a380sidebyside.png)
![A380 Alone](/img/pc/a380alone.png)
![A380 in Case](/img/pc/a380incase.png)
### First Impressions
Seeing as how I needed to run the Sparkle at a PCIe 2.0 x4 Link, thanks to be being on a B450 motherboard which I go into more details about on my [Arc A750 PCIe 2.0 x4 Benchmark](/posts/arc-pcie-benchmark/), as well as my experience [switching from B450 over to X570](/posts/b450-to-x570), I encounter quite a bit of issues.

#### The Issues
Here are few of the main issues I encountered from memory:
1. Qt apps would cause my entire compositor to lag when opening/shifting through dropdown entries. This happened in all sorts of Qt-based apps such as Strawberry music player and OpenRGB.
2. Hyprland was just straight up laggy - turning on the debug overlay I saw that the card was struggling to maintain equilibrium with my monitors (1 2560x1080@200 and 2 2560x1080@90) refresh rates. I'm not entirely sure if this was just because of the very low bandwidth of PCIe 2.0 x4, paired with the latency of being routed through the chipset, or if the card was just struggling. I'm fairly sure it was a mix of both.
3. Adding onto point number 2, moving windows would also cause my compositor's fps to, put simply, *die*. Lag spikes were a given especially when moving windows between monitors, which I found interesting. This honestly sucked given the buttery-smooth nature of Hyprland and its animations normally - making me want to pull my hair out at every fps drop and lag spike.
4. Turns out, the card itself is ~~pretty~~ very slow. Being in the performance ballpark of a GTX 1650/1650 Super, the card just wasn't cutting it for things like the [Anime4k](https://github.com/bloc97/Anime4K) upscaler which I was playing around with at the time, finishing off Shiki (pretty anime btw, would recommend). Now sure, this was definitely partly due to the terrible PCIe link, *but still*, I expected $200 in today's age to get you a lot more, (especially given that the A750 could be picked up for only about $100AUD more new).

### The VM Experience
Running my Windows 11 VM off of the 2070 Super, which was in my 3.0 x16 PCIe slot, I didn't see any performance penalties at all - that is, running straight off my monitor, without Looking Glass. Bringing Looking Glass into the picture was, *not the best of experiences*. I would honestly say that it was definitely usable at 1080p 60hz/fps, however, anything more than that would be pushing the absolute limits of what little bandwidth was available, leading to low FPS/UPS, stutters, and not a good time. However, the only way to alleviate this would be to get a higher-end chipset - one that supports PCIe bifurcation, allowing both GPU's slots to be routed straight to the CPU with 8 lanes each, which led me to go from [B450 to X570](Insert Link). But before this, I was like *why not* and decided to return this A380 for an A750.

## Second Card - Arc A750 LE
### Unboxing
Let me start off by saying *jeez, this card is sexy* (including the box). I was super excited I just opened it in the car...
![A750 Landscape](/img/pc/a750landscape.png)
![A750 Logo](/img/pc/a750logo.png)
My favorite part is the sticker!!
![A750 Sticker](/img/pc/a750sticker.png)

### Getting the Card In
I wasn't sure if the much chunkier A750 would fit in along with my 2070 Super - but luckily, it did:
![A750 in PC at First](/img/pc/a750in.png)
As you can see, the 2070 didn't really have any breathing room at all, leading it to get pretty hot at times (I think I saw 85C during a test session of BG3 - usually it'd max out at under 60C). 

### Better at PCIe 2.0 x4 Link?
Curiously, I had a much better experience with the A750 running at the same PCIe 2.0 x4 link through the chipset. Whilst, the intense lag present in the dropdowns of Qt apps was still present, moving windows between monitors in Hyprland was much less laggy and stuttery, making it a much better experience, although it was still there, just less intense. As you probably could've guessed - looking glass still ran pretty poorly, although slightly better I'd say - which could always just be placebo. I [benchmarked](/posts/arc-pcie-benchmark/) the card and compared the performance of both slots using Unigine Heaven, the results in terms of raw FPS were actually quite surprising. The bigger issue at hand was the latency of being routed through the Chipset for bandwidth un-intensive tasks. Also, the card had quite a bit of coil whine at first, but it became much quieter after a few days.

### With a Better Motherboard
Switching my config over to the MSI X570 Ace, which supports PCIe bifurcation (which I go into much more detail about [here](/posts/arc-pcie-benchmark/)), all the performance issues present in running the card off the PCIe 2.0 x4 slot on the B450 vanish. In terms of Looking Glass' performance, it's *amazing*, consistently high updates and frames, and not a stutter to be seen, especially when paired with the new D12 backend which is now the default, coupled with the KVMFR kernel module.  
![Shot of both GPUs](/img/pc/pca.png)
![Shot of PC](/img/pc/pcb.png)

I also ended up getting rid of my bottom fans, giving me the space to switch the cards around (seeing as both slots had equal bandwidth now). This reduced the temps of the 2070S back down to only a couple degrees C more than what its temperature would be without a second card in the mix too. 

## In Conclusion
Don't cheap out on your motherboard! Who knows if you'll turn into a crazy Linux VFIO user in a few years :D. But seriously, getting the change to play around with Intel's new GPUs was real fun, and I learnt a bunch of cool stuff in the process. 

Thanks for Reading!