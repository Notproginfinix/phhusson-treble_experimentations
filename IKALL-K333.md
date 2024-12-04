# 📱 IKALL K333

![IKALL K333 Image](https://ikall.in/wp-content/uploads/2023/06/2-600x600.jpg)

### General Details

* Processor : MT6739WA
* ARM ( armeabi_v7 )
* Binder 64
* Resolution : 240x320
* VNDK not in lite mode

### Exotic Features

* Keypad + Touch Screen
* Shipped with Android 12
* 4G Support
* Everything else like a normal Android phone.

## Steps To Install :

> !! Before proceeding, you gotta have some prior knowledge in these things as you have high chances of bricking your phone if you do not pay attention when messing with the device.

### 1. Unlock the bootloader

- Go to settings and turn on developer options.
- Enable OEM unlocking in developer options.
- Install the MediaTek USB Drivers ( If on Windows ) , in Linux its included by default.
- Properly install ADB and fastboot.
- Connect your device to a PC.
- Reboot to fastboot mode by command : `adb reboot bootloader`
- While in fastboot mode, run command : `fastboot flashing unlock` and a prompt will appear on device screen to confirm the changes and this 
  is the important part. the `#` button is volume up and `*` button is for volume down, so press the required button to confirm the request.
- After you pressed the button, your bootloader is now unlocked.

### 2. Flash the GSI Image

- Now download the required GSI Image ( Android 12+ Images Recommended ), you can test other images.
- Extract the image file and run `fastboot flash system <Path/To/Extracted/Image>`
- As you unlocked the bootloader, the system data is already erased, so now reboot by command `fastboot reboot` and for further flashing of 
  any image it is generally recommended to erase data before booting.

### 3. Readjust the screen DPI

- After the first boot, your screen elements would be very big, so to fix this you have to again connect your device to a computer.
- After connecting, run command : `adb shell wm density 120` , anywhere between 90(Very Small) - 120(Optimal) is fine.
- For ROMs not having USB Debugging enabled you can struggle a little with the DPAD and the touch screen would be hard to operate, so you 
  have to go to Setting > Display > Font or Display Text and Size, and then struggle a little bit playing around with the DPAD and screen to 
  enable USB debugging.

**4. Now your device is kinda ready to use, but some things do not work by default, see below.**

***

## Missing Features

- Two keybinds are not there by defaul, so to enable them you either have to make a Magisk module or unpack the system.img to make changes. Basically you have to edit Generic.kl to add the values , `key 227   STAR` & `key 231   CALL` .

- To get bluetooth properly working, disable A2DP offload option in Treble Settings and in some ROMs the voice call might not work properly so to fix that you enable "Voice In Call Route' option in Treble Settings.

- You can still play around with the device and new features.

***

## In case of any bricking or mistakes, you can always use mtkclient, but make sure to backup your stock system and boot image first before doing anything.

Submitted by @FreezyKaif






