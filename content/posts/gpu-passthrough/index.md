+++
title = 'RX6700m VFIO VM Passthrough'
date = 2023-12-06T08:28:24-04:00
draft = false
+++
## Background
Originally, I wasn't completely sure if passing through a Radeon laptop GPU, such as the RX6700m in my MSI Delta 15 would be possible, since all the tutorials I could find were for Intel + Nvidia or AMD + Nvidia. However, thanks to [Asus Linux's awesome passthrough tutorial](https://asus-linux.org/wiki/vfio-guide/), I was able to get my GPU passed through to my Windows 11 VM, as well as getting Looking Glass working, creating a great way to ~~use Microsoft Word at 240 fps...~~ I mean game :)

## Following The Tutorial
The tutorial was pretty straightforward, I was already using [supergfxctl](https://gitlab.com/asus-linux/supergfxctl) to switch between Hybrid and Integrated graphics modes, and the VFIO mode helped me easily get my dGPU geared up for my virtual machine. In terms of the libvirt hooks, I basically copied most of what was covered in the tutorial, apart from the Nvidia specific optimizations of course, however I did have to make a few alterations which I'll get into later. However, once the VM booted and I could see the dGPU in Windows task manager, I had a complete **Eureka Moment**!

## Errors I Occured
As I was getting the VM set up, I encountered a couple of problems:
### 1. Radeon Drivers Kept Crashing / Warning Triangle in Device Manager
This one had me pretty confused and distraught at first, however the fix ended up being simple. I had just forgotten to pass through the GPU's audio driver as well. I didn't think this would be a big deal since I wasn't planning on using HDMI/DP audio, but turns out the GPU won't function properly without its second half. So basically, make sure to pass through all the bits of your GPU, even if they're in different IOMMU groups.

### 2. Virt-Manager / Laptop Hard Freezes When Shutting Down VM
I figured this one had something to do with supergfxctl switching back from VFIO to Integrated mode via the libvirt hook, which was mentioned in the Asus Linux guide. To fix this one, I simply just added a ```sleep 3``` in the VM's poweroff hook just before ```supergfxctl -m Integrated``` was run. I'm not really sure what this meant, I'm guessing by default, the VM doesn't have enough time to completely unhook the GPU, which causes the entire system to just crash. I originally thought this might've been a Hyprland/Wayland specific issue, but I guess not.

Thanks for Reading!