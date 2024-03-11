+++
title = 'How To Disable The dGPU On The MSI Delta 15'
draft = false
date = 2023-10-10T06:28:24-04:00
summary = "Diving into this the Delta 15's advanced BIOS."
+++
## Background
If you're like me and have got an Msi Delta 15 or similar Msi laptop with a dGPU, you can probably disable it to get way more battery life, since even light apps can randomly cause it to turn on for no reason.

## Hidden Bios
Straight out the box, you haven't got much options, as seen below.
![Stock Delta 15 Bios](/img/laptop/bios1.jpg)
 However most Msi laptops come with a neat hotkey to enable a bunch of wild and wacky Bios settings. The hotkey is Left Alt + F2 + Right Ctrl + Right Shift - (just make sure you don't have the fn lock on as it won't work with it on).

## Warning
Make sure not to change anything that sound like it may brick your laptop, as chances are - it might, hopefully not though.

## Settings To Change
I've personally found that changing the settings under the Advanced -> AMD PBS tab does the trick (I've included a brief explaination of what I *think* each setting does.):
- Special Display Features: HybridGraphics -> Disabled (Disables the system's 'Hybrid Graphics' mode technically, but doesn't do enough to stop the dGPU from being used all the time.)
- Discrete GPU Hotplug Mode: Enhanced Mode -> Basic Mode (Likely makes it so that the GPU cannot be changed while the system is active.)
- Discrete GPU HPD Circuitry: OR Circuitry -> Pulse Circuitry (No idea lol)
- Discrete GPU's Audio and USB Port: ROM Strap/Default -> Disabled (Disabling features of the dGPU?)
- Discrete GPU's SSID/SVID: Manufacturer -> Keep Default Setting (By default, the DGPU's card ID is 0, and the integrated GPU's is 1, this makes it so that the dGPU uses the 'default' setting, which allows it to be disabled.)
![First Group of Settings](/img/laptop/bios2.jpg)


To disable the card even more (if that's how it works)...
Under Advanced -> Demo Board -> PCI-E Port, set Device 1 Fun 1's ASPM Mode to L0s Entry, and its Hotplug Mode to Hotplug Inboard. I presume these settings make the dGPU go into it's highest level of sleep by default, and set the default card to the onboard GPU respectively.
![Second Group of Settings](/img/laptop/bios3.jpg)

## What Happens
After making these changes, the laptop should boot up into Windows or Linux or whatever you're using with the red power light on, indicating the dGPU is active for a few seconds to a minute. After that, if everything worked out, it should switch to the white light, and the dGPU shouldn't turn back on, even if doing demanding tasks until these settings are changed back. Moreover, if you're using Windows, the dGPU should have vanished from task manager's system information - I've found that only changing a few of these settings can lead to the dGPU still being in task manager, and thus allowing Windows to still access it. I've also found that in Linux, sometimes doing a system info command like neofetch causes the light to turn red, however the dGPU is once again absent from neofetch, and the light turns back white shortly, so while this isn't a 100% fix for disabling the dGPU, it still works pretty well most of the time.

## Or... If you're on Linux
Just use Asus Linux's [Supergfxctl](https://gitlab.com/asus-linux/supergfxctl), it's way less buggy and hacky, and works with other laptops apart from Asus ones, like the Msi over here. It also works with both Nvidia and AMD dgpus!

