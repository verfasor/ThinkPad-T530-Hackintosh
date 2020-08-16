[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/mighil) [![捐赠](https://img.shields.io/badge/%E6%8D%90%E8%B5%A0-%E6%94%AF%E4%BB%98%E5%AE%9D-blue)](https://res.cloudinary.com/mighil/image/upload/v1578647638/donate-to-mighil.png) [![捐赠](https://img.shields.io/badge/%E6%8D%90%E8%B5%A0-%E5%BE%AE%E4%BF%A1-green)](https://res.cloudinary.com/mighil/image/upload/v1578647638/donate-to-mighil.png)

**DISCLAIMER: You're nothing but an a-hole if you sell EFI folder (config) that's readily available for free.**

**Update: The repo contains files for both Mojave and Catalina. The guide in the readme.md is only applicabe to Catalina. The guide for Mojave is available [on my website]( https://m1q.net/thinkpad-t530-hackintosh).**

# Lenovo ThinkPad T530 Hackintosh Config for Catalina.

**Fork or star, it's your call.** 

The repo contains EFI Folder (Clover files, config.plist, and BOOT) required to install/run Thinkpad T530. Hackintosh Catalina/Mojave.

![ThinkPad T530 Hackintosh](https://m1q.net/wp-content/uploads/2020/01/thinkpad-t530-hackintosh-catalina.jpg)

## My ThinkPad T530

Specs: i7 3740QM, 16GB Memory, 256GB SSD + 256GB SSD + 1TB HDD, NVIDIA NVS 5400M (N/A for Hackintosh)

![Mighil.com's T530](https://preview.redd.it/pz73e34bnd941.jpg?width=960&crop=smart&auto=webp&s=a24ebcd4663a0e79442950126b7a34ed8685eaab)

## #README

- Proceed with caution.
- Tested on macOS Catalina 10.15.2.
- EFI folder is N/A for Opencore bootloader. Go ahead though, if you know what you're doing.
- Do a Vanilla install if possible. I haven't tested a direct update from Mojave.
- The EFI folder is applicable to SSD hot-swap also. ie, if you're planning to swap SSD from a MacBook Pro to ThinkPad 530.

## BIOS Settings

Use the BIOS settings as mentioned below.

### Disable DGPU

Disable dGPU. The process is quite simple. Go to BIOS Setup -> Config -> Display and set the Graphics Device as “Integrated Graphics.” Also, disable the OS Detection for NVIDIA Optimus. Make sure it looks like the attached image below. Then, select Save & Exit.

![ThinkPad T530 Hackintosh BIOS Settings](https://res.cloudinary.com/mighil/image/upload/c_thumb,w_600,g_face/v1555925341/blog/ideal-bios-set-up-for-egpu-thinkpad530.jpg)

### Select UEFI Only

Go to BIOS Settings → Startup, select UEFI only. 

### Disable CSM Support (Only if the USB doesn't booting initially)

Go to BIOS Settings → Startup, disable CSM support.

![ThinkPad T530 Hackintosh BIOS Settings](https://camo.githubusercontent.com/194409231f53350510cac72c24f4b6c144ca28d2/68747470733a2f2f6d696768696c2e636f6d2f77702d636f6e74656e742f75706c6f6164732f323031392f30372f78323330742d62696f732d63736d2d6e6f2e6a7067)

## WiFi

Inbuilt intel-WiFi adapter won't work out of the box.

Atheros AR5B95, Lenovo part number 20002357 is a macOS supported/Lenovo-whitelisted card available for T530, X230 etc. You should add IO80211Family.kext from [this repo](https://github.com/mighildotcom/X230-Hackintosh/tree/master/10.15.2/EFI/CLOVER/kexts/Other) to Kexts/Other after installing that card.

Alternativly, you can flash the BIOS and remove the whitelist if you plan to use Broadcom WLAN cards.

Stick with a nano-USB WiFi adapter (something cheap based on Realtek) if you don't want to alter your hardware.

Refer to [Chris1111's repo](https://github.com/chris1111/Wireless-USB-Adapter-Clover) for package installer and Kexts if you own a Realtek 802.11n or 802.11ac USB adapter.

I added Realtek WLAN kexts (RtWlanU.kext & RtWlanU1827.kext) to use with my Comfast USB Wi-Fi adapter. You can safely remove it.

## What Else Doesn’t Work? 

- MiniDP 
- Fingerprint reader 
- Card reader

## How to create a bootable macOS Catalina USB install drive? (on MacOS)

[Refer to this guide from 9to5mac](https://9to5mac.com/2019/06/27/how-to-create-a-bootable-macos-catalina-10-15-usb-install-drive-video/)

## How to create a bootable macOS Catalina USB install drive? (on Windows)

1. Install [Transmac](https://www.acutesystems.com/scrtm.htm) on a Windows machine. It has a 15-day trial period and works flawlessly flashing DMG files to USB.

2. Download the latest [MacOS 10.15.2 with clover DMG file from here](https://mirrors.dtops.cc/iso/MacOS/daliansky_macos/) or other sources you come across Google SERP.

3. Download the EFI folder from this repo.

4. Download [Clover Configurator for macOS](https://mackie100projects.altervista.org/download-clover-configurator/) (latest version).

5. Connect a 16 GB USB flash drive.

6. Open Transmac. In the left pane, right-click the USB Drive and select Format Disk for Mac

7. Again in the left pane, right-click the USB Drive and select Restore with Disk Image. Then select the DMG file I mentioned in (2). Flashing process will take a few minutes depending on the size of .dmg and speed/port of the USB drive.

8. Install [DiskGenius](https://www.diskgenius.com/).

9. Locate the USB drive in DiskGenius. Delete the EFI folder and replace it with the new EFI folder. 

10. Plug the USB drive into the ThinkPad T530 and boot from USB.

11. Format the disk drive to APFS, install macOS Catalina, and restart the system.

12. Connect Hackintosh system to the Internet via LAN cable, USB tethering or a Mac-compatible external WiFi adapter.

13. Download & install Clover Configurator on MacOS. Open EFI partition and copy -> paste the the EFI folder once more. 

14. You may use [Karabiner-Elements](https://pqrs.org/osx/karabiner/) if the keyboard mappings (command and option) are acting up.

All the best.

### Support
![Donate](https://res.cloudinary.com/mighil/image/upload/v1578647638/donate-to-mighil.png)

