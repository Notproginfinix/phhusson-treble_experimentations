# General Mobile GM 8 Go / GM 9 Go

Basic   | Spec Sheet
-------:|:-------------------------
CPU     | 4x 1.5 GHz ARM Cortex-A53
SoC     | MediaTek MT6739
GPU     | PowerVR GE8100
Memory  | 1 GB
Android Version | 8.1 GO
Storage | 16 GB
MicroSD | Up to 64 GB
Battery | 3500 mAh (removable)
Display | 720 x 1440 pixels, 5.5"
Rear Camera  | 13.0 MP
Front Camera | 5.0 MP
Release Date | May 2018 / Feb 2019

# How to unlock the bootloader
## Use fastboot to unlock your bootloader
2. Enable developer options
3. Enable OEM Unlocking
4. Reboot into mtk preboot by pressing volume up + power and select fastboot via the volume buttons (instructions should be on the screen of the shiny black rectangle)  or boot into fastboot via the adb command `adb reboot fastboot`
5. Type in `fastboot oem unlock`

## Use mtkclient to unlock your bootloader
1. After following the guide on how to install mtkclient (which is https://github.com/bkerler/mtkclient here)
2. Open mtkgui
3. Take a whole backup of everything other than userdata (you may need it later)
4. Go into "flash tools"
5. Press unlock bootloader.

# What is working?
* Fingerprint sensor (GM 8 Go only)
* Calling (VOLTE is not tested)
* Notification light
* Cameras
* Touch
* Vibration
* WiFi and bluetooth
* Speakers

# Bugs
* Bootlooping sometimes on GSI's
* UI glitches
* Pasccodes cause a bootloop

# Notes:
GM 9 GO is identical to this device, with a lack of a fingerprint sensor (loongruige - GM 9 Go)

GSI's are very buggy on this phone and not stable. (Tohru - GM 8 Go)

Android 11 aosp gsi's did not work for me. (Tohru - GM 8 Go)

Newer Android 10 builds sometimes work but will bootloop at some times (Tohru - GM 8 Go)