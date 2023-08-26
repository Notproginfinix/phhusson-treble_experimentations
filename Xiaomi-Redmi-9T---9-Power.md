# Xiaomi Redmi 9T/9 Power (lime)

## Requirements

- PC with latest ADB/Fastboot installed
- Stock image (I flashed the stock fastboot flash files)
- A Compatible GSI image (Typically system.img)

## How to flash a GSI image?

First of all, you have to find out what architecture your phone is. You can do so by installing Treble info (Xiaomi Redmi 9T is ARM64 AB). Then, make sure that both the stock image Android version as well as the phone architecture matches the GSI image. Once you have the necessary files, extract them; you should see at least a `system.img` If you don't see it, don't worry, `WhateverFileName.img` you see it's most likely the `system.img`, you can rename it to `system.img` if you want.

Depending of the image, you would have to flash different files other than `system.img`.

If there is a `vbmeta.img` file use:
```
fastboot --disable-verification --disable-verity flash vbmeta vbmeta.img
```
For some GSI with Android version earlier than 13, you would have to reflash the original `boot.img` with verification disabled.
This image is found at the `images` folder located inside the stock image folder.

To reflash it with disabled verification, you must type:
```
fastboot flash --disable-verity --disable-verification boot boot.img
```
Then you must reboot into fastbootd. In order to do so, you have to type:
```
fastboot reboot fastboot
```
Give the phone some time to reconnect to the PC again and then type the following commands:
```
fastboot erase system
fastboot flash system system.img
fastboot reboot recovery
```
You may wipe cache and data partitions if it gives you an error.

## Working GSI builds
- Tested with [/e/ OS q Android version 10](https://doc.e.foundation/how-tos/install-GSI) (Recommended)
- Tested with [LineageOS "Light"](https://sourceforge.net/projects/andyyan-gsi/files/lineage-20-light/)
- Tested with [Google GSI](https://ci.android.com/builds/branches/aosp-android13-gsi/grid?)
- Tested with [Superior OS](https://github.com/ChonDoit/treble_superior_patches/releases)

Hardware support
|Component  |Working?| Comment                                                                               |
|-----------|--------|---------------------------------------------------------------------------------------|
|Camera     |√       |                                                                                       |
|Audio      |√/x     |Headphone jack doesn't work out of the box, but it can be fixed through Treble Settings|
|Display    |√       |Auto brightness works too!                                                             |
|Wifi       |√       |                                                                                       |  
|GPS        |√       |                                                                                       |
|Flashlight |√       |                                                                                       |

The components listed here are the ones I have tested. I suggest you to test others.

### To fix headphone jack
1. Go to **Settings**,
1. then go to **Treble Settings**,
1. in the audio section (it may be under Qualcomm features. It varies between GSI),
1. enable **Use alternate audio policy**. You may have to restart the phone.
