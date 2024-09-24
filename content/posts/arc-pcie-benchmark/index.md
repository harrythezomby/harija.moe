+++
title = 'Arc A750 PCIe Gen 2 x4 vs Gen 3 x16 Benchmarked'
draft = false
date = 2024-02-07T06:28:24-04:00
summary = "Testing the Intel Arc A750 at about 1/30th of its recommended bandwidth."
tags = ["PC", "GPUs", "GPU", "Intel", "Arc"]
+++


## Background
So I'd been wanted to try out GPU Passthrough on my PC, having tried it on my [Laptop](https://harija.moe/posts/gpu-passthrough/).

### Mobo Issues
My current motherboard (which was an MSI B450 Carbon Max), as with any B450 mobo had its second PCIe x16 slot wired as a x4 electrically, running at Gen 2 speeds through the Chipset. Now, this is pretty concerning due to latency and whatnot especially if you're *looking* to use [Looking Glass](https://looking-glass.io/). 

### Issues on Desktop
However, despite the few issues I faced on my Hyprland (running on the Arc on the 2.0 x4 slot, leaving the 3.0 x16 for my 2070 Super which was being passed through) such as opening dropdowns inside of QT apps lagging my entire desktop, and lag spikes when moving windows (especially between monitors), I was actually pretty surprised with the actual benchmark/fps results of the Arc running in the 2.0 x4 slot.

### Re-sizeable Bar
Before we get into the results, just keep in mind that re-sizeable bar, as well as above 4g decoding seemed to work on the 2.0 x4 chipset slot as well as the main x16 slot. If it didn't, performance would be a lot worse thanks to these guys relying heavily on these technologies. So, if you're planning on getting an Arc for a really old mobo/cpu combo - it will probably work, just not nearly as good as it could.

## Benchmarks
So, here are the results... Before we get into things - I'm by no means a pro benchmarker... As you can see the only results I really got are from Unigine Heaven since I honestly couldn't be bothered running a whole lotta other stuff.

![Benchmark Results](/img/pc/arcbenchmark.png)

### Highest Settings
As you can see, average fps on the highest settings was a less than 0.5 fps difference, with PCIe 2.0 x4 somehow gaining a 12fps edge in minimum FPS... This is definitely just a testing error or something... 

### Lowest Settings
Cranking the settings all the way down, still at 1080p, the gap increase quite a bit to the faster slot winning by around the 40-50 fps mark. However, curiously, the slower slot has once again managed to pull over double the minimum fps of the faster slot. 

## Conclusion
Obviously take this with a grain of salt... As once again, I'm probably a terrible benchmarker. However, I'm still pretty surprised with the results - illustrating that running at such low bandwidth *can* be viable, although is not ideal - thanks to the issues I mentioned earlier. 


