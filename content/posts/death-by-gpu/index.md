+++
title = 'Death by GPU (Nearly)'
draft = false
date = 2024-09-20T06:28:24-04:00
summary = "The dangers of optimistically trying a broken GPU..."
tags = ["PC", "GPU", "Used", "Broken"]
+++
## Background
For a while, I was searching for a cheap gpu to use as a simple display out for what I was turning into a little home server, built with my old PC parts, and ended up coming across a *broken* Gigabyte 4GB RX580 for $20 on Facebook marketplace. I thought I'd give it a shot to see if it was hopefully just a firmware issue or something, but boy was I wrong *and naive*... After meeing up with the seller from a nearby station and driving back home, I was excited to test the GPU which in hindsight was pretty dumb. There were some not so savoury signs that this GPU wasn't gonna lead to any good news, such as the backplate being slightly bent from the get go.
![Image (Cbb lol)](/img/rx580/hold1.jpg)

## Testing the GPU Without PCIe Power
I began by replacing the NVS 285 (lol) currently in my old PC with the RX 580, plugging it into the main x16 PCIe slot. For the first run, I decided to keep the 8 pin power disconnected, just to see if anything would work without it out of curiosity. Powering on the PC, I noticed that the RGB on the card did light up, although nothing further happened, with the video out remaining blank, and if I recall correctly, my mobo's VGA debug LED lighting up. Turning the PC off, I then proceeded to test it with the power connected from my CM Mwe.
![Image (Cbb lol)](/img/rx580/incpcoff.jpg)
![Image (Cbb lol)](/img/rx580/inpcrgbclose.jpg)
![Image (Cbb lol)](/img/rx580/inpcrgb.jpg)

## Testing the GPU With PCIe Power
After plugging in the 8 pin power cable, I flipped the switch to my power supply back on, but as soon as I hit the power button to my PC, a massive spark flew out of the GPU or the PCIe slot or something, followed by a breeze of smoke and the lovely smell of burning electronics. Freaking the heck out, I quickly turned off all power (although the mobo had shut off my itself) and I was dying inside since I thought I might've fried my poor little mobo or power supply with this cursed card. Regrettably, I wasn't recording since I didn't really expect this in the slightly, although it definitely would've made a good video in hindsight.

## Did I Kill my Mobo?
Luckily, after replacing the dumb 580 with my trusty 18-year-old NVS 285, I could see that both my main PCIe x16 and the electrically x4 x16 slot were both still working, as well as all other obvious functions of the motherboard and power supply too. This offered me a little relief amongst the slight tinge of the smell of burnt electronics covering my room.

## Opening Up The Card
Without anything else to do, I decided to open up the card and look at what actually happened with the whole spark thing. Getting the shroud and the heatsink off was fairly straightforward, following along with a YouTube tutorial. Once I managed to get the heatsink off, I noticed that a MOSFET on the card was completely burnt to a crisp, meaning that there was obviously a short somewhere in the card when I powered it up. After talking to the seller a bit, he let me know that it was probably water damaged thanks to a leaking air con. Moral of the story being not to trust obviously broken GPUs and to always check for shorts, even more-so if it's something that's been water damaged hehe. 
![Image (Cbb lol)](/img/rx580/heatsink.jpg)
![Image (Cbb lol)](/img/rx580/core.jpg)
![Image (Cbb lol)](/img/rx580/burnt.jpg)

## Conclusion 
Finally at the end of this GPU saga, I put the card back together, planning to keep it on display as a sort of memoir recollecting a bad and cringe memory that I would prefer to keep buried in the past. My friend Sanuk wanted the card just since it looked kind of cool, so I ended up giving it to him, marking the end of my time with the cursed RX580. I also won't be buying anything Gigabyte ever again (queue the Gigabyte PSU bomb meme).

Thanks for reading!
