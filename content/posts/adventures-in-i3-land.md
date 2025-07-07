+++ 
date = "2020-04-11" 
title = "Adventures in i3 land" 
author = "Mats Hellman" 
description = "Some ramblings about i3 on my old X220."
keywords = "i3wm x220 lenovo tiling windowmanager"
+++

As a geek I do like a lot of the modern things. At work I spend my time working
 with device services ranging from cloud services like Intune to things like
 traditional printing in factory floors.

There is very little that get’s me as exited as opening a box with new hardware
 in it, but from time to time I feel the hardware improvements are eaten alive
 by the ever growing complexity of the software. So while I spend a lot of my
 time reading about new things, I also like to go back in time and take a look
 at what can be done with older hardware instead of throwing it away.  

As an example my daughter is using a Mid 2009 MacBook Pro for her needs at the
 moment. With an SSD and 8Gb of RAM it works a lot better than expected. I have
 a bunch of old ThinkPad’s that have been neglected for quite some time. One of
 them being an old X220, and it is the device I’m writing on at the moment.
 And speaking of writing, the keyboard on this thing is second to none. I’ve
 never typed on a better keyboard than the old Thinkpad’s. They are in my
 personal opinion better than any of the current keyboards and so durable.

![X220-001](/images/x220-001.jpg)

![X220-002](/images/x220-002.jpg)


Considering this device was released in 2011, almost 10 years ago, it still
 handles what I throw at it extremely well. I did not try Windows 10 in it
 although I think it would have ran decently as well, instead it’s now running
 Debian testing with the i3 window manager. A cold boot from entering the
 encryption password takes about 7 seconds to the desktop. So even by modern
 standards more than decent, in fact a lot faster than my 2018 MacBook Pro and
 even faster than my Surface Laptop 3.

 ### i3 window manager

Being fast does come with it’s downsides, if you don’t like them. For me, I
 don’t see it as a downside, quite the opposite. As the hardware is older I set
 out to use something lightweight. Tiling window managers have fascinated me for
 a while now and I thought this hardware could really benefit from one. So
 instead of the large WM’s in Linux I decided to go with i3 and for the login
 screen Slim DM. Both extremely light and extremely configurable.

![X220 Screenshot](/images/x220-scrot-001.png)

Finding your comfort with a tiling window manager might require some work, at
 least it did for me. As an example there are things that are so wired in my
 brain I have issues trying to change them. One such is the Windows + L key to
 lock the computer. My i3 configuration used the VIM keys to move between open
 windows, meaning H,J,K,L were bind to that movement. I changed them to the
 arrow keys, not perfect, but I do need my Windows + L to lock my session.

### Slimlock

As I stated above I use Windows + L to lock my screen. This is something really
 wired into my brain, leaving a computer I always do this, needed or not. i3
 has this functionality in i3lock and you can call that to lock your screen. I
 however wanted to use the same nice GUI that Slim provides me on startup.
  
I also wanted the system to lock whenever I put my computer to sleep or close
 the lid so slimlock had to be called in those cases as well.
  
My i3 config, contains,

```bash

# Lock screen
bindsym $mod+l exec “slimlock”

```

and I created the a new file in /etc/systemd/system/i3lock@.service containing;

```systemd

[Unit]
Description = Lock screen when going to sleep/suspend/hibernate

[Service]
User=%I
Type=simple
Environment=DISPLAY=:0
ExecStart=/usr/bin/slimlock
TimeoutSec=infinity

[Install]
WantedBy=sleep.target
WantedBy=suspend.target
WantedBy=hibernate.target
```

The combination works exactly as I want it to.

## Changes in hardware

To make the X220 a bit more modern I added 4Gb of RAM in it. I rarely go over
 4Gb in this but still, as I had some laying around I gave it some additional
 memory. The time of HDD’s in laptops is long gone as well, so I had a Samsung
 860 SSD 1Tb driver on my table I stuffed into the laptop as well. The
 combination of the SSD and 8Gb of RAM makes the X220 fly.  
  
Before doing anything else I pulled the whole ting into pieces and replaced the
 thermal paste on the CPU, it is as I said 10 years old so it was time to get
 this done. If you have ever taken a Lenovo or IBM ThinkPad apart you start to
 appreciate the way these things are built. No laptop is easy to pull apart but
 with the servicing manuals and no-stress this was a enjoyable moment. I also
 notice the fans rarely spool up after applying some Arctic Silver paste on the
 CPU and putting everything back together.  

![X220 maintenance](/images/x220-003.jpg)

## Can you really do something on it?

Counting the running laptops and desktops in my house I have 5 of them in daily
 use. I really do not work on the X220 but it is able to get things done. I’ve
 tried using many of the tools I use in my daily job on it and so far have not
 had a single issue or noticeable dip in performance. Microsoft Teams is
 probably what I spend the majority of my time collaborating in and it works
 flawlessly on this device. I use O365 for email and documents, and although the
 web-versions of Word, PowerPoint and Visio are not 1:1 with the desktop
 version’s I can still be as effective in them. If I need a Windows desktop I
 can even get into one in our Cloud services meaning I really could make this
 old-timer my daily driver if I wanted to. And for my job when designing
 services for the enterprise, if I can use it from this device then anyone can
 use them from whatever they want.

## What's next?

I’ve been reading about Coreboot quite a bit, the next step for this old Lenovo
 is to get rid of the old BIOS and clear out as much as possible from the Intel
 Management Engine, I don’t have to, but I want to. Tinkering is still fun.
  