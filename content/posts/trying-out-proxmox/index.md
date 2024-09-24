+++
title = 'Trying Out Proxmox'
draft = false
date = 2024-09-21T06:29:27-04:00
summary = "My experiences with testing out Proxmox VE."
tags = ["PC", "Linux", "Virtualisation"]
+++
## Introduction
So, thanks to having a second PC just practically laying around after basically upgrading everything (although with an 18 year old GPU), I thought I'd give Proxmox a try after hearing lots of good things about it. I'd been wanting to create a home server, however seeing as I didn't have a decent GPU which could handle transcoding and stuff, I've been keeping my server-y and NAS related self-hosted programs on my main workstation (i know, laugh at you want :p). But nevertheless, I wanted to give Proxmox a try and learn the basics of it and its web UI, since I was sure my old 3600X could handle at least a couple of VMs going at once. 

## Installation
For the installation, I opted for the graphical installer, even though I was running off of the NVS 285 which I had previously tested, and struggled to even output `sddm` without severe artifacts and occasional blanking, just hoping for the best. However despite this, the little card actually managed to power through the installation pretty well,  leaving me with the tty by the end of it.

## Messing Around
Rather than doing anything directly on the PC, I SSH'ed into it from my main PC to run commands, as well as playing around on the web UI. I started by creating myself an Arch VM, which went pretty smoothly, since much of the options and workflow were similar to that of `virt-manager` and `libvirt` which I use all the time on my workstation for my Windows VM. I also noticed that thanks to Proxmox using a network bridge straight out of the box, the VM was seen as an actual device on my router, which its own unique local IP address, which is nice to have without any further setup like with QEMU/Libvirt. After that, I tried a Windows VM too, which also worked pretty good - I was able to VNC into it from the web UI on my main PC, as well as connecting through SPICE. The Web UI itself was also pretty neat in that it lets you easily have a look at RAM, CPU and disk usage. 

## Later On
Seeing as I'm still using my workstation for lots of my self-hosted stuff thanks to not having a proper GPU yet, as mentioned above, I've still barely delved into everything Proxmox has to offer. In the future, I'm hoping to have all my media-related servers such as Jellyfin and Navidrome on a NAS-based distro/package in a VM, such as openmediavault, as well as a Windows VM like the one I already made for quick tasks that only Windows can do - using MS Office for example.  Although I'd probably have to use the ACS kernel patch for a lot of this stuff, seeing as my B450 board's IOMMU groupings aren't great, with the SATA controller and 2nd PCIe x16 (electrically x4) grouped up together with all the other chipset-based devices, but using the patch would probably be fine, since I doubt someone capable of exploiting it like the NSA is out to get me (I hope) :D.

Thanks for reading!