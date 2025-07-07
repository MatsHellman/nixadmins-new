+++ 
date = "2019-12-02T08:00:00+03:00" 
title = "MacOS : Unhide dock faster" 
author = "Mats Hellman" 
description = "Oh the tweaks I do with MacOS" 
+++

As I’ve stated I more or less cross paths almost on a daily basis with all the
major operating systems. Most of the time my main driver is the 2018 MacBook Pro
which is with me whenever I leave the comfort of the home-office.
  
Although the resolution is good on this device the dock at the bottom takes up
a bit of space. I must say I’m not a heavy dock user, I’ve learnt long ago to
use CMD+Space to find my applications, just like I use the Windows key in
Windows 10 and MOD+D in my i3wm on Arch Linux. In my normal configuration I keep
the dock hidden and if you keep the default values you, for a split second,
wonder if it’s coming out at all. So, tweaking it to appear faster felt like a
good idea. Three commands later and we are done. As always, this blog is mostly
so I don’t have to search information on this again and try to find my personal
sweetspot.
  
Open a terminal and run the following commands, in the following order:

```bash
$ defaults write com.apple.dock autohide-delay -float 0  
$ defaults write com.apple.dock autohide-time-modifier -float 0.5  
$ killall Dock  
```
  
Now it does not feel like the Dock is stuck in mud somewhere, it actually
appears fast enough the few times I really need it.
  