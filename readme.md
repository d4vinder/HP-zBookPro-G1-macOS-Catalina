ZBookPro Catalina Install Guide

Things you’ll need:

A USB stick that is 16GB or greater
A HP zBookPro G1 laptop
Access to an Apple Macintosh to download macOS Catalina from Apple via the AppStore
Clover Bootloader https://github.com/CloverHackyColor/CloverBootloader/releases
Files from GitHub https://github.com/d4vinder/HP-zBookPro-G1-macOS-Catalina/

Prep: 
Take your USB stick and plug it in to your Mac.
Click find, and then type Disk Utility then click on the 'Disk Utility' app to open it. 
Locate the USB stick you just plugged in and format it as 'Mac OS Extended (Journaled), GUID Partition Map'. Give it the ‘Install macOS Catalina’ then hit erase.
Download Catalina on your Mac from the App Store.
Open Terminal and type the following command 
'sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/Install \macOS \Catalina —nointeraction’
 you will be asked for your password, then hit [Enter]. You will prompted for a ‘y’ confirmation. Wait until the process completes, it takes several minutes.
When completed, download clover and install it using the following options; 'Clover for UEFI booting only’ & 'Install Clover in ESP’
Take the EFI.zip folder downloaded from GitHub, extract it and copy to the EFI mounted partition to where you just installed Clover. Overwrite the existing EFI folder that’s already there ﻿

BIOS:

Power the laptop on and install OSX as you normally would on an Apple Mac. Be sure to set the BIOS as follows BIOS settings before you do.
To start, set BIOS to defaults.
UEFI boot is enabled (hybrid/with CSM for best result)
secure boot is disabled
disable fast boot
disable "LAN/WLAN switching", if available
disable "Wake on LAN" and "Wake on USB”

Install:
Unplug the installer USB and plug it in to the USB 2 port on the rear left of the zBook
Power the laptop on and select Install macOS Catalina from the Clover Boot Menu. 
Continue to install OSX as you normally would on an Apple Mac. Ensure you’ve formatted the destination drive in the zBookPro to 'Mac OS Extended (Journaled), GUID Partition Map’. Using Disk Utility when you reach the installer on the zBook.

Post Install:
Once you’ve booted in to macOS and you’ve reached the desktop, copy the clover installer over to your zBook and install it, same as you did in the Prep phase above.
Copy the EFI.zip from the GitHub repo and paste it over, replacing the EFI folder on zBook Boot drive. 
Restart and enjoy your new Hackintosh on your HP zBook 15.
