# Device

AOSP boots, WiFi, cellular data works, sound works

## Steps to install

First you need to Disable VBMETA

Go to bootloader and flash vbmeta.img (https://t.me/infinixnote30indonesia/125898) using this command

- `fastboot --disable-verification --disable-verity flash vbmeta vbmeta.img`

Flash GSI IN TWRP

Enter TWRP terminal (https://telegra.ph/Terminal-TWRP-08-01)

Write this in twrp terminal
- `lptools remove product_a`
- `lptools create product_a 335872` (Do not change this value)
- `lptools resize system_a` `4617089843` or `5368709120`(4.3GB system or 5GB system)
- REBOOT TO RECOVERY
- After that, flash this product_gsi.img (https://t.me/UdgUpdates/46) to the product partition (https://telegra.ph/Product-img-07-31)
- Select GSI img files, Install GSI to the system partition (https://telegra.ph/System-img-07-31)
- Format DATA
- Reboot System

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Works |
| Speaker / Mic             | Works |
| Headphone                 | Works with "module" |
| USB DAC                   | Works |
| USB OTG                   | Works with "module" |
| GPS                       | Works |
| Bluetooth                 | Works |
| NFC                       | Works |
| WiFi                      | Works |
| SIM / Mobile Data / Voice | Works |
| Tethering                 | Works |
| Proximity Sensor          | Works |
| Accelerometer / Gyroscope | Works |
| VoLTE                     | Works with "IMS features / Force 4G Calling" |
| RCS Message               | Works |
| Fingerprint               | Works |
| Brightness                | Works |
| Auto Brightness           | Works with "module" |
| Offline Charging          | Works |
| Fast Charging             | Works |
| Display Refreshing Rate   | Supports 60/90/120Hz with "Misc features / Force FPS" |
| Double Tap To Wake Up (dt2w)  | Works |
| Vibration                 | Works |

## Tweaks and Fix
[Module Patch GSI Infinix Note 30/Pro v2.4](https://github.com/phhusson/treble_experimentations/files/13425550/patchgsi-infinixnote30all_2.4b.zip)
1. Fix Smoothness
2. Fix StatusBar
3. Fix Brightness X6883B (Note 30)
4. Fix auto brightness
5. Fix Clock position in statusbar
6. Fix USB OTG

Use as magisk/ksu module

---
Tested By: 
- Deca1708 - Infinix Note 30 - TrebleDroid Android 14
- rama982 - Infinix Note 30 Pro - TrebleDroid Android 14