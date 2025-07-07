+++ 
date = "2020-04-21T08:09:26-07:00" 
title = "Lenovo X220 audio control in i3wm" 
author = "Mats Hellman" 
description = "Note to self on how to setup audiocontrols on the X220 in Debian." 
+++

This will serve as a note to myself as I found myself really looking for it
 every time I redid the device.

The Lenovo X220 has audio control buttons above the keyboard and they are nice
 to have working when using the device.
I use i3-wm myself and I have a old version of my i3 config in my Github,
 yes it’s time to update it as well so I don’t have to do this every time.

Anyway, this time the writing is for Debian, I’m using the testing version but
 I would assume this works in any of them. First and foremost, I am using the
 kernel module thinkpad_acpi and alsa, if you are using pulseaudio you need to
 look for the commands for that.

In my i3-config I have the following  
  
### Audio setting

 bindsym XF86AudioRaiseVolume exec “amixer -q sset Master,0 1+ unmute”  
 bindsym XF86AudioLowerVolume exec “amixer -q sset Master,0 1- unmute”  
 bindsym XF86AudioMute exec “amixer -q sset Master,0 toggle”  

Reload your i3 config and you should see the mute led turn on and of as you press it.
 Volume up and down works as well.
  