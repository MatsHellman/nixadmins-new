+++ 
date = "2020-12-03T08:09:26+03:00" 
title = "Issues with Coreboot and a workaround" 
author = "Mats Hellman" 
description = "Fresh installation of Debian refuses to boot automatically with Coreboot." 
+++

A while ago I stole the SSD drive from my Lenovo X220 to use it in another
device. The poor X220 has been dormant in storage ever since. This week I finally
had time to install the new drive in it and install Debian testing on it. 

## Oops we are not booting

Installation as with any Debian installation is really straight forward, but 
after the installation Coreboot dropped me to the EFI shell instead of booting 
the device correctly.  

Going to duckduckgo for information I found this article on Reddit,  
https://www.reddit.com/r/linux4noobs/comments/7iwhee/guide_hack_together_a_functioning_efi_boot_using/  

All the information is in the link, but to make sure I have it available in the future for myself I will document it here as well.  

To get the device to boot at all, run the command *map* in the EFI shell, this will show you all the devices EFI can see.  
I did not look at the BLK devices only fsN, in my case fs0 was the correct one. So using that as a base let's kick of the boot.  

```bash
$ fs0:\EFI\debian\grubx64.efi
```

```bash
  $ sudo bash #enter a root shell
  $ mkdir /boot/efi/EFI/BOOT #create the default directory where coreboot is looking
  $ cp /boot/efi/EFI/debian/* /boot/efi/EFI/BOOT/ #copy the EFI bits to the directory
  $ cp /boot/efi/EFI/BOOT/grubx64.efi /boot/efi/EFI/BOOT/bootx64.efi #copy or rename efi file to bootx64 instead of grubx.
```

This will allow you device to boot but with every reset you will have to follow this through. I guess the same goes if you upgrade some of the boot related components, like grub as the updates will not end up in the correct directory. So don't see this as a fix, it's a workaround.  
I will continue to look for a more premanent solution for the issue but for now I can boot my X220 and that does lower the urgency of the issue.  
