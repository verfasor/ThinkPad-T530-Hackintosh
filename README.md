[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/mighil)

# T530 Hackintosh Mojave Clover & Config.

**Fork or star, it's your call.** 

Grab the EFI Folder (Clover), plist, and BOOT required to install/run Thinkpad T530. Hackintosh Mojave.

![ThinkPad T530 Hackintosh](https://res.cloudinary.com/mighil/image/upload/v1574144992/hackintosh-t530-efi_p4lxxw.jpg)

## My T530

Specs: i7 3740QM, 16GB Memory, 256GB SSD + 256GB SSD + 1TB HDD, NVIDIA NVS 5400M (N/A for Hackintosh)

![Mighil.com's T530](https://res.cloudinary.com/mighil/image/upload/v1574145467/thinkpad-t530-clover-efi-hackintosh_ikt4cl.jpg)

### Launchpad

![ThinkPad T530 Hackintosh Mojave Launchpad](https://res.cloudinary.com/mighil/image/upload/v1574146587/thinkpad-t530-hackintosh-mojave-launchpad_xciuem.png)

### Display Resolutions Settings

![ThinkPad T530 Hackintosh Display Resolution Settings](https://mighil.com/wp-content/uploads/2019/11/thinkpad-t530-hackintosh-display-resolution-settings.png)

## #README

- Proceed with caution.
- N/A for Opencore bootloader. Go ahead though, if you know what you're doing. 
- EFI-swap recommended. I haven't tested these settings against the latest version of Clover.

The EFI folder is applicable for Vanilla approach and SSD hot-swap (just replace/paste EFI folder - not recommended though.) 

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

## What Doesn’t Work?

- Inbuilt WiFi, you can hack BIOS/install a Mac-compatible WiFi card. I highly recommend an external device like Comfast CF-811AC for the time being.
- MiniDP 
- Fingerprint reader 

## How to create a bootable macOS Mojave USB install drive? (on MacOS)

[Refer to this guide from 9to5mac](https://9to5mac.com/2018/06/18/how-to-create-a-bootable-macos-mojave-10-14-usb-install-drive-video/)

## How to create a bootable macOS Mojave USB install drive? (on Windows)

1. Install [Transmac](https://www.acutesystems.com/scrtm.htm) on a Windows machine. It has a 15-day trial period and works flawlessly flashing DMG files to USB.

2. Download the latest [MacOS 10.14.X with clover DMG file from here](https://mirrors.dtops.cc/iso/MacOS/daliansky_macos/10.14/) or other sources you come across Google SERP.

3. Download the EFI folder from this repo.

4. Download [Clover Configurator for macOS](https://mackie100projects.altervista.org/download-clover-configurator/) (latest version).

5. Connect a 16 GB USB flash drive.

6. Open Transmac. In the left pane, right-click the USB Drive and select Format Disk for Mac

7. Again in the left pane, right-click the USB Drive and select Restore with Disk Image. Then select the DMG file I mentioned in (2). Flashing process will take a few minutes depending on the size of .dmg and speed/port of the USB drive.

8. Install [DiskGenius](https://www.diskgenius.com/).

9. Locate the USB drive in DiskGenius. Delete the EFI folder and replace it with the new EFI folder. 

10. Plug the USB drive into the ThinkPad T530 and boot from USB.

11. Format the disk drive to APFS, install macOS Catalina, and restart the system.

12. Connect Hackintosh system to the Internet via LAN cable, USD tethering or a Mac-compatible external WiFi adapter.

13. Download & install Clover Configurator on MacOS. Open EFI partition and copy -> paste the the EFI folder once more. 

14. You may use [Karabiner-Elements](https://pqrs.org/osx/karabiner/) if the keyboard mappings (command and option) are acting up.

![ThinkPad T530 Hackintosh Settings for Karabiner Elements](https://res.cloudinary.com/mighil/image/upload/v1574146218/t530-hackintosh-karabiner-elements_gefjwu.png)

All the best.
