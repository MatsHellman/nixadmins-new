+++ 
date = "2019-11-22T08:00:00+03:00" 
title = "Hey, where's my Yubikey?" 
author = "Mats Hellman" 
description = "Case of the missing Yubikey on ArchLinux" 
+++

This post is just for myself to remember this as it was behind so many clicks
on the oh so phenomenal [ArchWiki](https://wiki.archlinux.org "ArchLinux Wiki").
  
For many years I have been using multifactor authentication where possible.
SMS in the beginning and today mostly authenticator application(s) or the
Yubikey(s). These together with a decent password manager make me feel at least
a bit more secure with all the accounts and passwords I need to remember.
If you are looking for a password manager to help make your life a bit laid back
when it comes to password management I recommend you take a look at
[BitWarden](https://bitwarden.com "Bitwarden Password Manager").

## Problems ...

Some nights ago I decided to install Arch Linux on one of my workstations. Easy
and fast installation with a very customizable system, what’s there not to like 😀
  
Since the system is so highly customizable, you need to read. And I do really
love learning something new, I just have an issue remembering a week down the
line what I did. So that’s why this post is here. This way I can find it fast
the next time I need it.
  
So, the problem was that my Yubikey did not show up in Firefox. First thing
first you always check dmesg to make sure the device is even recognized.
And so I did,

```bash
usb 1-2: new full-speed USB device number 5 using xhci_hcd  
usb 1-2: New USB device found, idVendor=1050, idProduct=0120, bcdDevice= 5.02  
usb 1-2: New USB device strings: Mfr=1, Product=2, SerialNumber=0  
usb 1-2: Product: Security Key by Yubico  
usb 1-2: Manufacturer: Yubico
```
  
And there it was. At least my system knew about it. Some
[duckduckgo.com:fu](https://duckduckgo.com "DuckDuckGo")
later I found an article on
[ArchWiki Fido U2F authentication](https://wiki.archlinux.org/index.php/Firefox/Tweaks#Fido_U2F_authentication "ArchWiki Link")
pointing me to the
libu2f-host package. Easy as 1,2,3 fire up pacman install the package and
restart the browser and my Yubikey is back in business.

```bash
$ sudo pacman -S libu2f-host  
resolving dependencies...  
looking for conflicting packages...  
```
  
This as stated above is not meant to be a guide on MFA or the Yubikey, just a
placeholder for me to remember what I did if I ever run into it again.
  