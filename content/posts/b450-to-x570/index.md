+++
title = 'B450 to X570'
draft = false
date = 2024-02-08T06:28:24-04:00
layout = "posts"
summary = "My experience upgrading to an X570 board from a B450 in terms of VFIO and PCIe stuff."
+++
## Background
Seeing as my old MSI B450 Carbon Max was [struggling](/posts/arc-pcie-benchmark/) to keep up with running two gpus off of it thanks to the 2nd slot being routed through the chipset at PCIe 2.0 x4 speeds, as well as the issues I describe which arose from running my host GPU through that slot, which I go into more detail [here](/projects/gpu-adventures). I was also pretty bummed out at having to live with one NVMe drive, seeing as using a second GPU disabled the slot, thanks to the B450 chipset not having enough PCIe lanes - upgrading would also allow me to passthrough another one or more NVMe drives to my Windows VM. I began to look for a good used X570 mobo to replace it. Seeing as X570 boards are now discontinued, unlike B550 boards which continue to be sold, I decided Facebook Marketplace would be the best place to find my new mobo.

### Why not B550?
I opted for a used X570 over a new B550 which are roughly the same price for a few reasons:
1. Better IOMMU grouping
2. More PCIe lanes
3. More likely to have the 'premium' features I was looking for such as PCIe bifurcation to run both cards through the CPU with 8 lanes each
4. Motherboards aren't known for dying too quickly, so I didn't mind getting a good quality used board at all

## New Board
### Browsing for Boards
On Facebook Marketplace, I found a few boards which looked good.
1. X570 Aorus Elite Wi-Fi for $200AUD
2. ROG X570E for $250AUD
3. MSI MEG X570 Ace for $250AUD

### The X570 Ace
Ultimately, I decided to go with the MSI X570 Ace - seeing as how it was the most expensive of the lot before being discontinued and how it had the most useful features to me. Compared to the Gigabyte board, it was overall just better - since tbf, they aren't even in the same class, so I was definitely willing to spend the extra 50 between them. As for the Asus, the only real difference that comes to mind is the Msi board's additional M.2 slot, seeing as both of them had more 'premium' features such as dual Ethernet. 


## Switching Out the Boards
Switching out the boards took quite a while - mainly due to my terrible cable management on the solid side of my case. Once I got the cables sorted, I was able to get my AIO off, followed by my CPU, M.2 drives, and all other power connectors. 

### RIP IO Shield
I was kinda lazy to remove all my case fan's and my AIO's rad so I kinda just had to yank the old board out - which bent the IO Shield a bit as well as the Wi-Fi antennas. No worries - should be fine... I hope... :')

### Getting the New Board in
Getting the new board in was pretty straightforward - the only things to note were the CPU power cables being a bit of a pain to plug in, since my radiator + fans which I couldn't be bothered taking out were blocking it sort of. Also, I wasn't able to screw in the mobo's middle screw - since one of the heatsinks were blocking it. Apparently lots of cases have a clip of sorts for this screw, which mine, as a budget case from a few years ago doesn't have... Makes sense, but all goods, should be fine with only one screw, especially the middle one missing.

## First Impressions
### Moment of Truth...
Luckily, I was able to get everything, minus a few jumbled ARGB cables up and working flawlessly. 

### What I Love!
- PCIe bifurcation :D
- Going from 1 gen 3 and 1 gen 2 (although not with the 2nd GPU in, so basically just the one gen 3) NVMe slot to 3 gen 4 slots!!!
- The BIOS is more or less the same, minus a couple of different options

### What I Don't
- Goofy OEM Boot Logo :p
- In my opinion, the RGB on the old board was better - while the magic mirror design on the Ace is interesting, the good old strip of leds on the B450 Carbon looked much better in my eyes. The bigger factor is that OpenRGB is unable to control each, or even a group of LEDs built into the mobo separately in direct mode, so basically its just RGB as opposed to ARGB. On the B450 Carbon you're able to control the built-in leds in groups of 2, which is much nicer for rainbow effects in particular. Much like the B450, the Ace is unable to have its ARGB headers resized in OpenRGB as well.

### Meh
- Only 4 SATA ports - I only use 2 SATA drives so this isn't too much of a problem for me. Honestly, I would definitely sacrifice 2 extra SATA ports in favor of a 3rd NVMe drive, because of their added versatility for Vfio (not having to pass through the entire SATA controller in contrast)


Thanks for reading!
