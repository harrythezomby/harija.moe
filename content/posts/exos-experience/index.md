+++
title = 'The Exos Experience'
draft = false
date = 2024-09-21T06:29:28-04:00
summary = "My thoughts on using Exos enterprise drives at home."
tags = ["PC", "Linux", "Hard Drives", "NAS", "I spent way too long writing this"]
+++
## Introduction
So, after a couple of months of owning both a 12TB Seagate Exos X16, and then a 16TB X16 too a little bit later, I'd like to share my thoughts on using these loud little enterprise/server drives in my workstation, to store music, movies, etc.


The two drives:
{{< gallery >}}
  <img src="/img/hdd/new12.jpg" class="grid-w50" />
  <img src="/img/hdd/new.jpg" class="grid-w50" />
{{< /gallery >}}

## Price
Starting off with price, I got the 12TB drive for $215 AUD, and the 16 for about $258 (in hindsight, I probably should've saved up initially for a 16TB rather than a 12), which comes out to about $17.9AUD (12.2USD)/TB for the 12TB drive, and $16.1AUD (11USD)/TB for the 16TB drive, which is honestly really cheap for this much storage. This was mainly due to the fact that I bought these as OEM drives, rather than proper retail drives with an actual in-store warranty and stuff. I did however get these from one of [OzBargain's](https://www.ozbargain.com.au/) favourite hard drive sellers, who are based in Hong Kong (but ship some drives out from Australia, my first came from HK, but the second was from Sydney), who do a 3 year warranty on everything, so I should be good on that front. I'm not gonna name any names though till I get sponsored ;p. 

## First Impressions
If you do decide to go through this route of OEM drives from 3rd party sellers however, (and honestly even with retail drives just to be safe), I'd recommend testing your drives thoroughly - more on that in a little bit. When I got the first drive, and eventually the second, I noticed both of them had 2021 manufacture dates, which is slightly concerning but hey, if it works it works. 

After doing a bit of research on everyone's opinions online, there are a couple of likely scenarios here. The first is that these drives are simply just old stock, which didn't end up being used or sold for whatever reason, and the second is that they are used and have had their SMART data wiped. Honestly, it's practically impossible to tell which scenario is true, but rolling with my motto once again - if it works it works :).

From here on, I'll just talk a bit about the 12TB drive which is what I got a few months earlier than the 16TB. 
 
After opening up my PC and getting the drive installed into the case's drive bay, along with its own SATA data and power cable, I powered on my PC. The noise was honestly pretty starling at first, as the drive sounded like the scrape of sandpaper mixed with someone banging on a table, at least paired with the acoustics of my PC case and table, however I later learnt that this was basically normal for these enterprise drives (whose prime demographic wouldn't care in the slightest about noise level). 

However, there was a little issue in that with the drive plugged in, my Arch wasn't booting up properly - going into maintenance mode instead for some reason as all my other drives (including my boot drive SSD) were failing to mount. I was slightly worried that this was due to the drive being dead or something, having been shipped all the way from HK, although I managed to fix it by initialising the drive with a GPT table and formatting it with an FS (I chose btrfs which may be a little controversial ;)) curiously. After that, the it was smooth sailing ahead with 12 juicy TB (which i ended up filling in only a few months :D).

### Testing
In order to test the 12TB drive, i used the tried and tested `badblocks`, which you can read more about on the [Archwiki here](https://wiki.archlinux.org/title/Badblocks), TLDR being that it's a really old program designed for floppy disks, but can still be made to work with larger modern drives by passing 32-bit integer limitations with a few launch options/parameters. I did the default read-write test, which is *really excessive*, but seeing as it was my first hard drive in ages, I was like why not. The read-write of the four default patterns took about a week to complete, meaning I had to sacrifice a bit of sleep quality over this thanks to the drive's noise, but it was definitely a lot quieter than when in normal operation, thanks to the test running in a sequential nature through the drive's heads, rather than randomly seeking through the heads like when browsing files for instance.

## After the Second Drive
After a few months of having the first drive in operation, I was coming close to filling it up all the way, so I went ahead and got a second 16TB drive, which came from Sydney this time, from the same seller. I also ordered a pack of adhesive Velcro strips to hopefully absorb some of the noise and vibrations of having a second drive packed in with the first, however this would later prove to be a pretty dumb idea. Excitedly returning home on the day the package came, I got to work installing it in my PC, along with [De-RGBifying it](/posts/de-rgbing) (TLDR: for less cables and not having 3 RGB/fan hubs crammed in the back).

### Screwed by Velcro
So, remember how I mentioned the Velcro strips being a bad idea? Well, I ended up being stupid and forgetting how Velcro works with hooks and loops (they are called `Hook And Loop Fasteners` after all), and how you need to pull them upward to unfasten them. My idiotic 12am self ended up filling my drive bay and the side of my drive to the brim with this Velcro tape, and ended up getting it stuck right in the drive bay *the wrong way around*!! After sacrificing a knife, a ruler, and a lot of my sanity, I finally managed to get the stuck drive out by prying it with these random long and flat objects by around 4AM. Fast forward to the next day, I managed to get everything installed properly with only a little bit of Velcro, and nothing too excessive, and luckily the drive was fine even after my abuse. 

Pictures of the stuck drive:
{{< gallery >}}
  <img src="/img/hdd/stuck1.jpg" class="grid-w50" />
  <img src="/img/hdd/stuck2.jpg" class="grid-w50" />
{{< /gallery >}}

Finally got it out, and got both drives in their proper position *with a lot less Velcro*:
{{< gallery >}}
  <img src="/img/hdd/inbay.jpg" class="grid-w50" />
{{< /gallery >}}

Plugging in the drive just to make sure it stills works:
{{< gallery >}}
  <img src="/img/hdd/testingwitharc.jpg" class="grid-w50" />
  <img src="/img/hdd/driveworking.jpg" class="grid-w50" />
{{< /gallery >}}

RIP Ruler 🙏:
{{< gallery >}}
  <img src="/img/hdd/ripruler.jpg" class="grid-w50" />
{{< /gallery >}}

### Testing
This time, for the second drive, I decided to take a different approach to testing it, instead opting to use the Archwiki's recommended method of spanning a cryptographic layer over the drive rather than using `badblocks`, which is outlined in greater detail once again in the [Archwiki over here](https://wiki.archlinux.org/title/Badblocks#Alternatives). In comparison to running `badblocks` on the 12TB drive, this `cryptsetup` + `shred` + `cmp` approach took only a couple of days, although that was obviously due to this method only doing one pass by default, and me not really feeling like going too overboard with this once seeing as how flawlessly the previous drive had been working.

## Thoughts in Retrospect
### Sound
Looking at the sound of both drives together in retrospect, being right next to me on my desk basically, they are *loooud*. With some torrents going in the background, as well as my Jellyfin and Navidrome servers occasionally scanning, the drives along with the acoustics of my case and table sound kinda like a constant rumble with some occasional light banging (obviously describing a hard drive making *banging sounds* would normally be a cause for concern, although in this case it's most of a slight thump of the head moving back and fourth between platters, since once again, these are meant for servers and not your bedroom). However, with these in *my bedroom*, I honestly don't really mind, obviously this comes down to personal preference, but with my IEMs in or speakers going, the drives are barely audible. It does become more of a problem though when trying to sleep with my PC on at night, which is the one scenario in which I'm not a big fan of these drives. Although having a fan (this time an actual cooling fan that spins) running in the background is a good way to drown out the unbalanced and sometimes jarring of the drives running.

### Storage + Price
Ignoring sound for now, having this much storage for a much lower price compared to an SSD or a more consumer-orientated hard drive has been great. Being able to self host my Navidrome instance filled with nearly 350,000 songs (mostly in flac, wav or alac), as well as a Jellyfin server complete with dozens of Anime and movies has been amazing, especially thanks to being able to ditch streaming services completely whilst streaming 4k video to something like my TV directly through my LAN, meaning no buffering, stuttering or internet issues to worry about at all. 

### Speed
Honestly speaking, the last time I really dealt with a hard drive was back in my last laptop that had a hard drive only and no SSD - which was a little HP x360 Pavilion from around 2013, with what was a 400GB 5400rpm drive IIRC. Thanks to this, as well as my previous devices with hard drives as their boot drives, such as my HP Compaq 8510w laptop and the Pentium 4 desktop before that, I'd always grown up thinking that hard drives were *reallly* slow. However in modern times,  that is not the case at all, with these drives reading and writing with speeds up to 260MB/s, which may still sound pretty slow in comparison to an NVMe or even SATA ssd, but for static media such as music and movies, there isn't really an issue at all, with things like 4k video streaming as mentioned above working flawlessly. The only thing to take note of is that scanning your library in things like Navidrome and Jellyfin will take quite a bit longer with a hard drive, but that's more of a one time or rare thing to go thorough, which wouldn't really affect day-to-day use.

### Cooling
Thanks to these drives being 7200rpm, and being pretty relentless thanks to noise constraints being thrown out the window, ideally they need some active cooling for the best lifespan. Initially, when I was rocking the 12TB drive only, I wasn't using any active cooling (i.e., any fans in the back partition of my fish tank case), and because of this, the drive ran pretty hot, running at around 40-50C most of the time, which while being over the 'recommended' temperature, is still fairly far from the absolute max temperature of 60C. When using the drive like this, the maximum I hit was 52C, which I'd definitely not want to be running at all the time. 

After getting the second 16TB drive, I installed 2 120mm case fans next to my case's drive bay in the back partition, securing them (to the best of my abilities) with some 3M VHB double-sided adhesive - ideally, some zip ties would come in handy here for most cases, but my case didn't really have space or a place for them to hook onto. After adding in these fans and adjusting their fan curve accordingly to run at a comparatively high speed compared to the other fans in my case, and even with the second drive added in as well, the temperature of both drives hover around 30-38C, hovering near the 33-35C mark most of the time even under slight load, with temps only picking up to the latter 30s under very high load. Thanks to these fans, both drives stay at a much more comfortable temperature, most of the time a fair shot away from the recommended maximum of 40C, meaning that these drives really do benefit quite a bit from some active cooling, although it's still not the end of the world if you can't actively cool them.

I initially tried one fan only:
{{< gallery >}}
  <img src="/img/hdd/onefan.jpg" class="grid-w50" />
{{< /gallery >}}

But there was room for one more, so I was like why not:
{{< gallery >}}
  <img src="/img/hdd/twofans.jpg" class="grid-w50" />
{{< /gallery >}}

Tried my best to secure them with one end of cut 3M VHB strips:
{{< gallery >}}
  <img src="/img/hdd/stuckon.jpg" class="grid-w50" />
{{< /gallery >}}

Now the placement might seem off or counter intuitive, which yeah it probably is (since this was the only angle they, or even one would fit in), but they've still helped quite a bit with keeping the drives cool nevertheless. 

## Conclusion
Using these hard drives and orientating a lot of my day to day media consumption into much of a self-hosted thing has been really good fun, and proved to be an amazing choice ultimately. If you're like me and don't really mind the noise, but would like a bunch of storage for cheap, these Exos drives (or even a WD/HGST Ultrastar) are a pretty solid option.