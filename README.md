# MSI-MAG-Z490-TOMAHAWK-i7-10700-OpenCore-

Hello,

I have successfully installed MacOS Catalina 10.15.5 on my i7 10700 non K runing on MSI MAG Z490 TOMAHAWK.

**Current Bootloader: OpenCore 0.6.0**

# Hardware

- Intel I7 10700
- MSI MAG Z490 TOMAHAWK
	- Audio: REALTEK/ALC1200-VD1
	- 1x Realtek® RTL8125B 2.5G LAN + 1x Intel I219V 1G LAN
	- 1x USB-C port
- RAM: 32GB DDR4 Corsair 3000MHz
- GPU: XFX AMD Radeon RX 580 GTS XXX Edition 8GB

# Working

- [x] **Tested with macOS Catalina**
- [x] **Audio**: Realtek ALC1200-VD1 (AppleALC.kext, layout-id=7, device-id=0xA170, FakeID.kext, FakePCIID_Intel_HDMI_Audio.kext)
- [x] **USB**, all ports
- [x] **iGPU UHD630 Headless mode**
- [x] **RX 580 works OOB no kext used**
- [x] **iMessage/FaceTime**
- [x] **Sleep/Wake**
- [x] **Shutdown**
- [x] **Restart**

# Instructions

1. Create an MacOS Catalina 10.15.5 bootable USB. You can do this on a real Mac
 	 - Go into the app store and search for Catalina, once downloaded you can find the Installer.app inside Applications folder.
   - Earse the USB by using Disk Utility and rename the USB to MyVolume
   - Create bootable USB by using this command: sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolum
  
2. Mount the EFI-partition of the "Install macOS Catalina" disk.
   - You can do this using the Terminal with the following commands:
   - diskutil list
   - Once you have found the disk for example disk0s1 runt the following command to mount the EFI partition:
   - sudo diskutil mount disk0s1
   - Enter the password and the EFI partition should be mounted 
   
3. Delete all folders and then copy my EFI folder to the root of the EFI-partition
4. Go to EFI/OC and open the config.plist with a plist Editor (You can use PlistEditor Pro use google for this)
5. Once the config.plist is open navigate to PlatformInfo/Generic and paste your serials for MLB, SystemSerialNumber and SystemUUID. (you can use CorpNewt's GenSMBIOS)
6. Boot from the bootable USB and install macOS.
7. Once macOS is installed you can copy the EFI folder to the EFI partition of the internal SSD/HDD
