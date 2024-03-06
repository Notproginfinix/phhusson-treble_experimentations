# Specs
* MT6739 SoC
* 1GB RAM
* 16GB ROM
* Single 13MP camera
* Fingerprint sensor (optional if you have GM 9 go which is basically GM 8 go with no fingerprint)


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

# What is working?
* Fingerprint sensor
* Telephony (not fully tested I did a testing emergency call)
* Notification light
* Cameras
* Touch
* Vibration
* WiFi and bluetooth
* Speakers
* Device encryption

# Bugs
* Bootlooping sometimes on GSI's
* Whole UI literally dying 
![IMG20240307002508](https://github.com/phhusson/treble_experimentations/assets/114253931/37be40d3-4f2e-43c3-9f8c-c7fadbe7d312)
![IMG20240307002533](https://github.com/phhusson/treble_experimentations/assets/114253931/b766faa6-2cbf-421f-820b-3340b14bc3d0)
* Device encryption is sometimes causing a bootloop

# Notes:
GSI's are very buggy on this phone and not stable. System partition is also very small since this is an Android go device (1.29 GB to be precise).
Android 11 aosp gsi's did not work for me. 
Newer quack (android 10 builds) builds sometimes work (optional) but will bootloop at some times