## `Xiaomi Poco M5 (Global)`

The [GSI](https://github.com/naz664/crDroid_gsi/releases/download/v2024.01.22/crDroid-10.1-arm64_bgN-Unofficial.img.xz) I used in question

Steps to Install

***


 BACKUP EVERYTHING you can!

 Unlock your `bootloader`

 When it comes to this device,you **MUST** flash [Stock](https://miuirom.org/phones/poco-m5) ROM (Fastboot ROM variant) to return to A partion

Before flashing Stock ROM you will need to follow [this](https://telegra.ph/Fix-Error-Flashing-please-read-carefully-06-26) guide.

Before flashing custom recovery please flash [product](https://t.me/UdgUpdates/46)

 Download this [TWRP](https://sourceforge.net/projects/premiumprjktrom/files/Rock/Twrp_3.7.1-12.0_rock-Unofficial.img/download) 

# WARNING!!! #

This Device uses vendor_boot for recovery so:

1. fastboot --disable-verification flash vbmeta vbmeta.img
2. fastboot flash vendor_boot twrp.img
3. fastboot reboot recovery


***

## In TWRP

> Download this [system resizer](https://t.me/PocoM5oprek/247076/368305) and flash through twrp

> REBOOT TO RECOVERY

> Pick Any [GSI](https://github.com/phhusson/treble_experimentations/wiki/Generic-System-Image-%28GSI%29-list) from the list, Flash GSI to [system partition](https://telegra.ph/System-img-07-31). 

> Format data

> Reboot system


***

And, We are done! Hope you enjoy your new OS of choice!



