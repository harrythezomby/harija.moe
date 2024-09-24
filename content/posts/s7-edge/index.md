+++
title = 'Android 14 on the S7 Edge'
draft = false
date = 2024-09-21T06:29:24-04:00
summary = "Setting up and testing Lineage OS 21.0 on the 8-year-old Galaxy S7E."
tags = ["Phones", "Android", "Custom Rom"]
+++
## Introduction
Here's just a little post about my experiences of getting an unofficial Lineage OS 21.0 ROM (which is Android 14) up and running on this old phone. The ROM in question is [this one by Ivan_Meler](https://xdaforums.com/t/lineageos-21-0-android-14-signature-spoofing-ota-updates-for-s7-edge-exynos.4655852/), which you can find on the XDA forums. After already rooting/installing custom ROMs on a handful of Samsung devices at around this generation, the process was once again pretty straightforward.
![Phone with OG Rom](/img/s7/ogphone.jpg)

## Installation
As mentioned above, getting everything installed was pretty simple. I started by enabling OEM unlocking within the phone's developer settings (while still on the stock ROM of course), before then rebooting into download/flash mode, whatever you wanna call it. After getting Odin up and running on my Windows VM, and plugging the phone in via USB (which, if you're interested, I passed one of my PC's USB controllers through to my VM), I was able to flash TWRP. Then booting into TWRP, I transferred the ROM, as well as Magisk (I didn't feel like installing some GApps this time around), and then installed the two of them after wiping the phone.
![Phone in download mode](/img/s7/downloadmode.jpg)

## Thoughts
After getting the phone all set up, I was honestly shocked at how fast and snappy it was, considering it was a nearly eight and a half year old phone running Android 14. However, with the advent of 90 and 120hz screens on basically every modern phone, including plenty of the super budget ones, scrolling on the S7E's 60hz screen definitely wasn't anywhere near as satisfying as on a modern phone, even modern phones in a much lower class money-wise such as my current daily-driver - the Motorola Edge 20 Fusion. 

Something else I was really impressed with was the battery life on this thing, considering it was still using its 6-8 year old battery. From 80%, I noticed it lasting for up to a week+ on standby, paired with a little bit of light use. This probably had to do with not installing any Google Apps, which clearly otherwise eats away at a large chunk of your battery.

## Conclusion
Ultimately, if you have an old phone such as the S7E lying around, modding it with a custom ROM could turn out to be a fun and interesting experience, possibly breathing new life into an abandoned phone, and may even exceed your expectations like with me and the S7E.

## Gallery
{{< gallery >}}
  <img src="/img/s7/home.jpg" class="grid-w33" />
  <img src="/img/s7/qs1.jpg" class="grid-w33" />
  <img src="/img/s7/qs2.jpg" class="grid-w33" />
  <img src="/img/s7/cam.jpg" class="grid-w33" />
  <img src="/img/s7/a14.jpg" class="grid-w33" />
{{< /gallery >}}

Btw, if you we're wondering how I got my quick settings tiles and notifications to look the way I did, I used [Mahmud0808's Iconify](https://github.com/Mahmud0808/Iconify), a great FOSS tool to customise the look of AOSP ROM based devices (i.e., Lineage OS, Google Pixels, etc., it works great on my Motorola as well!)


Thanks for reading!