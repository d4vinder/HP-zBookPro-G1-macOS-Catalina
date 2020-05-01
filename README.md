# HP-zBookPro-G1-macOS-Catalina
Complete EFI for HP zBookPro for macOS Catalina 10.15.4

ZBookPro Catalina Install Guide

Things you’ll need:

1. A USB drive that is 16GB or greater

2. A HP zBookPro G1 laptop

3. Access to an Apple Macintosh to download macOS Catalina from Apple via the AppStore https://apps.apple.com/gb/app/macos-catalina/id1466841314?mt=12

4. Clover Bootloader https://github.com/CloverHackyColor/CloverBootloader/releases

5. Clover Configurator https://mackie100projects.altervista.org/download-clover-configurator/

5. EFI directory files from GitHub https://github.com/d4vinder/HP-zBookPro-G1-macOS-Catalina/blob/master/EFI.zip?raw=true

USB Installer Prep: 
1. Take your USB drive and plug it in to your working Macintosh.

2. In the top right-hand corner, click the 'Find' icon, and then type 'Disk Utility' then click on the 'Disk Utility.app' application to open it. 

3. Locate your installer USB drive you just plugged in to the Macintosh and format it as:
- 'Mac OS Extended (Journaled), 
- GUID Partition Map',
- Give it the name; ‘Install macOS Catalina’, then hit erase.

4. Download Catalina on your Mac from the Apple AppStore. It will download to your Applications folder as 'Install macOS Catalina.app'

5. Open Terminal and type the following command, without the quotes:

'sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/Install \macOS \Catalina —nointeraction’

You will be prompted for your password to the Macintosh, enter this then hit [Enter]. You will prompted for a ‘y’ confirmation prior to formatting your USB drive. Wait until the process completes, it will take several minutes.
 
6. When the formatting has completed, download the Clover bootloader and install it to your Catalina Installation USB device [u]NOT THE MACINTOSH YOU'RE CURRENTLY WORKING ON!![/u] using the following options; 'Clover for UEFI booting only’ & 'Install Clover in ESP’, leave any default options checked.

7. Take the EFI.zip folder downloaded from GitHub, extract it and copy to the EFI mounted partition to where you just installed Clover. Overwrite or delete the existing EFI folder that’s already there prior to pasting the contents of EFI.zip

BIOS Prep:

Power the laptop on and install OSX as you normally would on an Apple Mac. Be sure to set the BIOS as follows BIOS settings before you do.
- To start, set BIOS to defaults.
- UEFI boot is enabled (hybrid/with CSM for best result)
- secure boot is disabled
- disable fast boot
- disable "LAN/WLAN switching", if available
- disable "Wake on LAN" and "Wake on USB”

macOS Catalina Install:

1. Unplug the installer USB drive from the Macintosh and plug it in to the USB 2 port on the rear left of the HP zBook

2. Power the laptop on and select 'Install macOS Catalina' from the Clover boot menu. 

3. Using Disk Utility when you reach the installer on the zBook Ensure you’ve formatted the destination drive (the disk you are installing to) in the zBookPro using the follwing settings:

- Mac OS Extended (Journaled)
- GUID Partition Map
- name this macOS Catalina [or whatever you like]

Now, continue to install OSX as you normally would, navigating through the  Apple installation process. Your machine will restart a number of times during the install process, this is normal. 

Post Catalina Install:

1. So far, the modified bootloader is only present on the USB, your installation. This means without the USB drive present, your newly installed Catalina will not boot on the laptop without it. Once you’ve booted in to 'macOS Catalina' on your zBook and you’ve reached the desktop, copy the Clover bootloader installer pkg over to your HP zBook 'macOS Catalina' drive and install it same as you did in the USB Prep phase above, this time changing the destination of the install to 'macOS Catalina' [or whatever you named your macOS boot drive].

2. Copy the EFI.zip from the GitHub repo and paste it over, replacing the EFI folder on zBook Boot drive. 

3. Change the Serial Number for your new Hackintosh from the one that is included in the config.plist in the downloaded EFI.zip - otherwise, multiple accounts using the same serial number will lock your AppleID. To change the the Serial Number, download 'Clover Configurator' and mount the EFI partition for your macOS Catalina boot drive. Locate and open the 'config.plist' file in the EFI partition. On the right-hand memu click on SMBIOS, then on the main pane, under System, click on 'Generate New' next to the serial number field.

4. Restart and enjoy your new Hackintosh on your HP zBook 15.

Enjoy. 
