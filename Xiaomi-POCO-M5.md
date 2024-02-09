# Xiaomi Poco M5 (Global)

The [GSI](https://github.com/naz664/crDroid_gsi/releases/download/v2024.01.22/crDroid-10.1-arm64_bgN-Unofficial.img.xz) I used in question
***


**CAUTION : Backup all of your data before proceeding!**

## Precautions

* Unlock your `bootloader` first, you can use [Mi Unlock](https://en.miui.com/unlock/index.html) for it.

* When it comes to this device,you **MUST** flash [Stock ROM](https://miuirom.org/phones/poco-m5) (Fastboot ROM variant) if you found out your device active slot is on B, you can check your active slot simply using a Fastboot command: `fastboot getvar current-slot`

* Before flashing Stock ROM you will need to follow [this](https://telegra.ph/Fix-Error-Flashing-please-read-carefully-06-26) guide.

* Download this [TWRP](https://sourceforge.net/projects/premiumprjktrom/files/Rock/Twrp_3.7.1-12.0_rock-Unofficial.img/download) 

## Warning

This Device **uses vendor_boot as the recovery partition**, so flashing a custom recovery will be exactly like this:

> 1. `fastboot --disable-verification flash vbmeta vbmeta.img` _Disabling Verification for VBMeta to avoid dm-verity issue_
> 2. `fastboot flash vendor_boot twrp.img` _Flashing the custom recovery_
> 3. `fastboot reboot recovery` _Reboot phone to recovery_


***

## Using Custom Recovery (Teamwin/OrangeFox/Pitchblack)

> 1. Download this [system resizer](https://t.me/PocoM5oprek/247076/368305) and flash through twrp

> 2. REBOOT TO RECOVERY

> 3. Pick Any [GSI](https://github.com/phhusson/treble_experimentations/wiki/Generic-System-Image-%28GSI%29-list) of your choice from the list, Flash GSI to the [system partition](https://telegra.ph/System-img-07-31). 

> 4. Format data

> 5. Reboot system

**For changing GSI-to-GSI, you can simply skip step number 1**


***


And, We are done! Hope you enjoy your new OS of choice!



