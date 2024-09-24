+++
title = 'Uses + Setup'
draft = false
date = 2023-08-15T06:28:24-04:00
layout = "about"
summary = "What I mainly use on my computers + my dotfiles and setup."
tags = ["Harija", "Uses", "Setup", "Software"]
lastmod = 2024-09-21T06:28:24-04:00
+++
## Software Uses
Here's a bit of info on what I use day-to-day on my computers.
All dots and other configs can be found here, at my dotfiles repo:
{{< github repo="harrythezomby/dotfiles" >}}

### Desktop Stuff
Original AGS Setup:
![First Setup](/img/uses/agsdesktop.png)
Updated AGS + Rofi Setup:
![Second Setup](/img/uses/newdesktop.png)
Current Waybar + Rofi Setup:
![Third Setup](/img/uses/newdesk.png)
- I use vanilla [Arch Linux](https://archlinux.org/) btw. I love its customisability and the fact that it only has as much bloat as I want it to!
- For my window manager/wayland compositor, I use [Hyprland](https://hyprland.org/). Hyprland's silky smooth animations are great, especially on high refresh monitors.
- Along with Hyprland, I used use [Aylur's GTK Shell](https://github.com/Aylur/ags) for creating cool widgets - such as my top status bar. However now I'm mainly using [Waybar](https://github.com/Alexays/Waybar) for simplicity's sake. For my launchers I use the Wayland port of [rofi](https://github.com/lbonn/rofi), and [swaync](https://github.com/ErikReider/SwayNotificationCenter) for notifications.
- [Kitty](https://sw.kovidgoyal.net/kitty/) is my go-to terminal, mainly since I've grown used to it, being Hyprland's default terminal and all. It's pretty fast and customizable too which is nice. Paired with Kitty, I use fish for my shell, along with the [Starship](https://starship.rs/) prompt.
### Other Applications
- [Neovim](https://neovim.io/) with [LazyVim](https://www.lazyvim.org/) for basic text-editing, including editing config files.
- [VSCode](https://code.visualstudio.com/) for heavier coding and bigger projects.
- [KDE Dolphin](https://wiki.archlinux.org/title/Dolphin) for file browsing. It's pretty feature-rich, looks decent paired with a Qt theme, but for me it's just for those times im not ls -l'ing or cd'ing inside a terminal.
- [Joplin](https://joplinapp.org/) for all my school and personal note taking. I love how it's privacy focused with E2EE, as well as its expandability and theme-ability with plugins and custom CSS. I'm also running an instance of Joplin Server, which helps me get all my notes synced up, and lets me share them via URL if need be. Check out my custom Joplin theme at my [dotfiles repo](https://github.com/harrythezomby/dotfiles).

### VPS + Sites
- I run [Arch](https://archlinux.org/) on my VPS. It's actually been very stable believe it or not.
- I build all my sites with [Hugo](https://gohugo.io/), which is great for creating fast static sites. This one in particular's running the [Blowfish Theme](https://blowfish.page/), which I also love.

### Self-Hosted 
- [Jellyfin](https://jellyfin.org/) for my home media server - Anime, Movies, TV Shows, etc.
- [Navidrome](https://www.navidrome.org/) for organising and serving my 22+TB of FLACs :D.
- [Immich](https://immich.app/) for backing up photos as a good self-hosted alternative to Google Photos.
- [Komga](https://komga.org/) to organise and serve my Manga and Light Novels.
- [Transmission](https://transmissionbt.com/) for torrents, used in the [compose-transmission-wireguard](https://github.com/sebdanielsson/compose-transmission-wireguard) docker.
- [Joplin Cloud](https://github.com/laurent22/joplin/blob/dev/packages/server/README.md) to sync my Joplin notes, and to publish them on the internet.

## Setup
Here's a bit on my current productivity and gaming setup.
### PC
**OS:** Arch Linux + Hyprland  
**NVMe SSD:** Crucial P3 1TB  
**NVMe SSD:** Crucial P1 1TB  
**NVMe SSD:** ADATA Legend 850 Lite  
**SATA SSD:** WDC Green 240GB  
**SSHD:** Seagate Firecuda 2TB SSHD 5400rpm  
**HDD:** Seagate Exos X16 12TB  
**HDD:** Seagate Exos X16 16TB  
**CPU:** AMD Ryzen 5 5950x  
**Host GPU:** Intel Arc A750 LE (Sexy)  
**Guest GPU:** Asus Dual Geforce RTX 2070 Super  
**RAM:** 48GB Corsair Vengeance Rgb Pro SL 3600mhz (2 x 8gb, 2 x 16gb)
**PSU:** Corsair RM850x  
**Motherboard:** MSI MEG x570 Ace  
**AIO:** Cooler Master ML360 Illusion  
**Case:** Antec C8 White  
**Sys Monitor:** AliExpress AX206 Via lcd4linux  

Original PC setup with the Antec DF600 Flux:
![PC with Arch](/img/pc/newsetup.png)
![PC](/img/pc/pca.png)

After moving to the Antec C8:
![PC](/img/c8/complete.jpg)

After getting rid of all the RGB:
![PC](/img/c8/dergb.jpg)

### Server
**OS:** Proxmox VE  
**NVMe SSD:** MSI M450 500GB  
**CPU:** AMD Ryzen 5 3600x  
**GPU:** Nvidia Quadro NVS285  
**RAM:** 2 x 8 Corsair Vengeance LPX 3200mhz  
**Motherboard:** MSI B450 Carbon Max  
**Case:** Antec DF600 Flux Princess Edition  
**PSU:** Cooler Master MWE 750 Gold  
*Btw, I'm just calling it a server to sound cool; I don't even use it right now lol.*
![Server](/img/uses/server.jpg)

### Laptop (MSI Delta 15 A5EFK)
**OS:** Arch Linux + Hyprland  
**SSD:** WDC SN730 1TB  
**SSD:** Micron 2200S 256GB  
**CPU:** AMD Ryzen 7 5800H  
**iGPU:** AMD Vega 8  
**dGPU:** AMD Radeon RX 6700M (working with VFIO passthrough to VM ^_^)  
**RAM:** 2 x Crucial CT16G4SFRA32A 16GB 3200mhz  
![Laptop](/img/uses/laptop.jpg)

### Peripherals
**Monitor 1:** MSI Optix MAG301RF 2560x1080 200Hz IPS  
**Monitor 2:** Lenovo L29W-30 2560x1080 90hz IPS  
**Monitor 3:** Lenovo L29W-30 2560x1080 90hz IPS  
**Mouse 1:** Logitech G402  
**Mouse 2:** Razer Deathadder Elite  
**Mouse 3:** Corsair Glaive RGB Pro  
**Mouse 4:** Attack Shark X3    
**Headset:** Corsair Void RGB Elite USB  
**Headphones:** AKG Y50 Taxi Yellow  
**Keyboard 1:** Epomaker Tide75 Pink (Stock Switches)  
**Keyboard 2:** HK Gaming GK61 (Akko CS Lavender switches)  
**Keyboard 3:** Corsair K68 Cherry Red  
**Speaker Set:** Altec Lansing 121i  
**Tablet For Osu:** Xp-pen G640  
**Wheel:** Deep Dish Logitech G923 w/ Logitech Shifter  


Old HK GK61 + Corsair Glaive Setup:
![Peripherals](/img/uses/peri.jpg)

Current Tide75 + X3 Setup:
![Peripherals](/img/uses/tide75x3.png)

## Audio
![IEMs](/img/uses/iems1.jpg)
### IEMs
1. Truthear Zero Red
2. Tangzu Wan'er S.G.
3. Kiwi Ears Forteza
4. Kinera Celest Wyvern Pro
5. KZ EDX Pro X
6. QKZ AK6
7. QKZ AK3 FiLe
8. Kinera Celest Phoenixcall
9. KZ Castor Bass Edition
10. KZ ZSN Pro 2
![IEMs](/img/uses/iems2.jpg)
{{< gallery >}}
  <img src="/img/uses/zerored.jpg" class="grid-w33" />
  <img src="/img/uses/waner.jpg" class="grid-w33" />
  <img src="/img/uses/forteza.jpg" class="grid-w33" />
  <img src="/img/uses/wyvernpro.jpg" class="grid-w33" />
  <img src="/img/uses/edxprox.jpg" class="grid-w33" />
  <img src="/img/uses/phoenixcall.jpg" class="grid-w33" />
  <img src="/img/uses/castorbass.jpg" class="grid-w33" />
  <img src="/img/uses/zsnpro2.jpg" class="grid-w33" />
{{< /gallery >}}

### TWS
1. Jabra Elite 3 (One side broken) 
2. Sony WF-C700N
3. KZ AZ15 Ear Hooks
![TWS](/img/uses/iems3.jpg)
![TWS](/img/uses/az15.jpg)

### TV Setup
**Receiver:** Marantz SR6004  
**Speakers:** 7.1 Setup with Jensen Speakers  
**TV:** 85" Samsung QN800B 8K
![Receiver](/img/uses/receiver.jpg)