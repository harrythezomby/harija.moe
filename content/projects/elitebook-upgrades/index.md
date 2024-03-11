+++
title = 'Hp Elitebook Upgrades'
date = 2023-12-06T06:28:24-04:00
draft = false
summary = "Upgrading the RAM and Storage on my old Elitebook while my main laptop was in RMA."
+++
## Background
While my MSI Delta 15 was in RMA, thanks to battery issues I might go into more detail about in a different post, I had to switch back to my old laptop for school, which was this 2019 Hp Elitebook 830 g6 I bought from my school back in 2020.

## Upgrades
- 1TB Adata Legend 850 Lite SSD
- A 16GB Crucial 3200mhz SODIMM Stick

## Opening It Up
Opening up the laptop was a piece of cake, just unscrewed the few Torx T5 screws on the bottom panel and with a bit of prying, it was off! The M.2 slot was right there on the board, and the two RAM dimm slots were under the little metal cover, which was a bit finicky to get off, but we got there eventually.
![Laptop without cover](/img/laptop/hplaptop1.jpg)

## Cloning the Old drive
After booting into my Gparted USB to clone the laptop's old Micron drive to the new Adata one via an M.2 to USB enclosure, I realized that I'd forgotten to disable the HP Drivelock feature which encrypts the drive when not in use off, and accessing the BIOS with the M.2 plugged in via usb seemed to crash it, so I had to open the laptop back up, disable Drivelock, and re-install the new ssd, which was a pretty stupid mistake. After that, I was able to clone the old drive's partitions (excluding the SWAP partition since I'd moved up from 8GB of RAM to 24, so I didn't really need it anymore). After fixing up some stuff on the Fstab and bootloader (which was GRUB in this case) my Arch install came back to life!
![Gparted](/img/laptop/hpgparted.jpg)

## Benchmarks and Info
- Here's what Dmidecode reported, I was a bit worried that the ram sticks would default to 2133Mhz, since I mixed a stock Samsung 4GB stick with the Crucial 16GB stick, and there's no option in the BIOS to manually adjust RAM speed and timings, but luckily it defaulted to 2400Mhz, which was the speed of the Samsung stick:
![Dmidecode](/img/laptop/hpdmidecode.jpg)


- Here's the KDiskMark results for the Adata SSD in this laptop, of course it's nowhere near the speed the drive is capable of, being bottlenecked by the PCIe Gen 3 limits of the laptop:
![KDiskMark](/img/laptop/hpadatabench.jpg)

## Other Cool Stuff
I'd also like to touch on some of the cool stuff about running Arch on the Elitebook:
- The Active Pen G3 that comes with the laptop works great with [Xournal++](https://xournalpp.github.io/), including pressure sensitive drawing
- [rot8](https://github.com/efernau/rot8) was also really fun to play around with, thanks to the near-instantanious screen rotation with it running in the background. unlike Windows
- Unfortunately, I don't think there are Linux drivers for the trackpad, at least I wasn't able to find any...

Thanks for reading!


