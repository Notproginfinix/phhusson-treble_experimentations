# S22 (Exynos)

## Steps to install

1.  Unlock Bootloader (Enable OEM Unlocking in Developer Options, power the phone off, hold Vol+&- while plugging in to your PC)
2.  Download the latest firmware for your device (You can use e.g. Samfirm - google it)
3.  Extract the archive, open up the super archive via 7Zip Z-Standard (NOT THE REGULAR 7-Zip), extract the recovery archive and then extract that one to get your own recovery.img
4.  Patch your recovery image - you can patch it with **[Johnx22's Patch-Recovery Tool](https://github.com/Johx22/Patch-Recovery) **

5.  To flash the patched recovery, extract the 'Patched-Recovery.zip' and flash the 'fastbootd-recovery.tar' via Odin (AP slot)
                   
*  _**Make sure to hold the power button and Volume Up as soon as the phone starts rebooting, otherwise the patched recovery will be overwritten by the Samsung one when the phone boots into OneUI**_
6.  After entering recovery, choose "Enter fastboot"
7.  Flash an ARM64 A/B GSI with fastboot:    `fastboot flash system image.img`
8.  Go back into recovery and Wipe Data and Cache
9.  Reboot!

## Steps to root a GSI

* Download and install **[7-Zip Z Standard](https://github.com/mcmilk/7-Zip-zstd/releases)**
* Open the AP firmware file (that you'd usually flash via Odin) with 7-zip ZS
* Extract the boot.img.lz4
* Open the the boot.img.lz4 with 7-zip ZS
* Extract the boot.img
* Download and install the latest **[Magisk Manager apk](https://github.com/topjohnwu/Magisk/releases)**
* Copy boot.img to your phone
* Open the Magisk app
* Choose "Select and Patch a file"
* Pick your boot.img
* Take that patched image from Downloads and put it on your PC
* Boot into fastboot via the recovery
* `fastboot flash boot <patched boot image name or whatever>.img` 
* Reboot
* It will bootloop so make the phone go into recovery once more, where it'll offer you to Factory Reset since the phone is having a seizure
* Perform that factory reset and reboot

## Telegram Group

[Telegram Group](https://t.me/+Ehf3IgzJw0k0NmE8)

## Hardware support

| Component                 |      Comment                                                      |
|---------------------------|-------------------------------------------------------------------|
| Camera                    | Works (Front and Back)  **                                        |
| Speaker / Mic             | Works                                                             |
| Bluetooth                 | Works (Tested only audio playback)                                |
| WiFi                      | Works                                                             |
| SIM / Mobile Data / Voice | Works                                                             |
| VoLTE                     | Unknown                                                           |
| Fingerprint               | Works                                                             |
| NFC                       | Works (Used 2FA key)                                              |
| Offline Charging          | Works                                                           |
| 120Hz                     | Enable in Settings > Phh Treble Settings > Misc features > Force FPS (Works from the get go along with Adaptive Refresh Rate in personalized PE builds from the Telegram group)          |
| Auto-brightness            | Works (It can be a bit wonky so do personalize the brightness levels to your needs once and you should be good)               |
| Proximity sensor            | Kinda works              |

---

**In the stock camera, everything should work but the quality is ass. With GCam, however, you get better quality at the cost of instability that you yourself have to tinker with to reach some stability.

Visit the Telegram group for up-to-date Google Camera setups (in the notes).

Tested By: https://github.com/JeikWazTaken - SM-S901B, Pixel Experience Plus 13 14.07.2023  - Tested on 14/07/2023 - Template created by @zguithues and @hackintosh5

