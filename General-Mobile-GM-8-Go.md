# Specs
MT6739 SoC
1GB RAM
16GB ROM
Single 13MP camera
Fingerprint sensor

# How to unlock the bootloader
## Method 1
### Use fastboot to unlock your bootloader
1. Update your phone to the latest available software version
2. Enable developer options
3. Enable OEM Unlocking
4. Reboot into fastboot by either using the preboot menu (combo is volup + power) or using adb
5. type in fastboot oem unlock

## Method 2
### Use mtkclient to unlock your bootloader
1. After following the guide on how to install mtkclient (which is https://github.com/bkerler/mtkclient here)
2. Open mtkgui
3. Take a whole backup of everything other than userdata (you may need it later)
4. Go into _flash tools_ 
5. Press unlock bootloader.

# Notes:
GSI's are very buggy on this phone and not stable. System partition is also very small since this is an Android go device (1.29 GB to be precise).
Android 11 aosp gsi's did not work for me. 
 