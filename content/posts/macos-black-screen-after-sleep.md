+++ 
date = "2019-12-03T06:00:00+03:00" 
title = "MacOS black screen after sleep" 
author = "Mats Hellman" 
description = "Fixing the MacOS black screen after sleep" 
+++

Yesterday I decided it was time to upgrade my MacBook Pro 2018 from Mojave to
Catalina. Easy update but in the future if someone tells you Windows 10 upgrades
are slow, ask them to try it on a Mac. I can update all Windows devices in my
house one by one faster than my Mac from 10.14 to 10.15.
  
Anyhow, this was not a post to beat down my Mac, I do still like parts of you 😀
  
After the installation was done all was well with my applications, homebrew kept
working and everything appeared to be just fine. Until this morning, like most
mornings I pulled my Mac and opened the lid waiting for the screen to light up,
but no. Touchbar (the worst idea ever by the way) was active but the screen was
black. After my first meetings of the day it was time to test if this still
happened. And yes, it did.
  
Some digging on the web and someone even had a fix to re-install the operating
system… What the … I’m not going to re-install. Haven’t reinstalled any of my
other computers either and hopefully the Mac is not this unstable that you have
to re-install just for an upgrade when the Windows installations are fine after
years and years of upgrades and Linux installations even more so.
  
The one common thing I found was that most fixes were deleting .kext files,
kernel extensions. Some even mentioned the specific files to delete, I however
did not have any of them but what I did have on my Mac was the DisplayLink
software as I use it with my Lenovo USB-C docking station. All is fair in war
and computer issues so:
  
Go to your applications folder and look up DisplayLink,
then run the Uninstaller.
  
It will ask you to reboot so you should, once done go find the latest driver
from [Displaylink.com](https://displaylink.com "Displaylink"). Install it, reboot and your black screen should be gone.
This of-course assumes you had DisplayLink installed in the first place :D.
  
As always the writing here is mostly notes for myself. If you had success with
the above, enjoy and you are welcome.
  