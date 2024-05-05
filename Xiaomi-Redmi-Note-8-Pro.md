## Overview

| Info | Value |
|-|-|
| Device codename | `begonia` |
| Release date | September 2019 |
| Stock ROM | Android 9 to 11 (MIUI 12.5) |
| VNDK | 30.0 |
| Compatible Images | ARM64 AB [vndklite] |
| CPU | Mediatek MT6785 Helio G90T|

## Hardware support
| Component | Status | Note |
|-|-|-|
| RIL | Working | GSM / HSPA / LTE |
| Double SIM | Working | |
| MicroSD | Working | |
| Display | Working | 60Hz |
| Camera 64MP | Working | limited to 16MP in standard cameras |
| Camera Macro | Working | |
| Camera Ultrawide | Working | |
| Camera Depth sensor | Working | used as 2MP lense in standard cameras |
| Camera Front | Working | limited to 5MP in standard cameras |
| Speaker | Working | |
| 3.5mm Jack | Working | |
| Mic | Working | |
| Bluetooth | Working | |
| WiFi | Working | hotspot as well |
| GPS | Working | |
| NFC | Working | not tested for payments |
| IR blaster | Working | |
| FM radio | Not Working | needs proprietary lib |
| Fingerprint | Working | |
| Offline Charging | Partially Working | boots to recovery |
| Notification LED | Working | |

## Software Support
| Component | Status | Comment |
|-|-|-|
| VoLTE | Not Tested | |
| Auto Brightness | Working | |
| Night Light | Working | |
| Notch overlay | Working | |
| D2TW | Working | Settings > Phh Treble Settings > Xiaomi features > Enable DT2W |
| Face Unlock | Working |

## Camera

TODO

## Installation

1. Update to latest vendor (via OTA or fastboot package if bootloader is unlocked)
2. Unlock bootloader (officially or via [mtkclient](https://github.com/bkerler/mtkclient))
3. Recommended: backup sensitive partitions (in case you inadvertently wipe IMEI)
    - `nvcfg`
    - `nvdata`
    - `nvram`
    - `persist`
    - `protect_f`
    - `protect_s`
4. Follow PHH flashing guide (see telegram note `#flash`)

## Uninstallation / Back to stock MIUI

### From a working device using fastboot

1. Download a full ROM package, usually marked as `Fastboot`, from [Xiaomi Firmware Updater](https://xiaomifirmwareupdater.com/miui/begonia/)
2. Verify `.tgz` archive hash (MD5 hash is provided on download page)
3. Open or extract `.tar` from `.tgz` archive
4. Extract ROM files from `.tar` archive to disk
5. Connect your device in fastboot mode (verify using `fastboot devices`)
6. Execute `flash_all` script (or `flash_all_lock` if you want to relock bootloader)
    - `.bat` for windows
    - `.sh` for linux
7. Device should reboot automatically, if not and no error was displayed try `fastboot reboot`
8. Device should boot on MIUI (on first boot splash logo can de displayed few minutes)

## Unbricking

If something went terribly wrong and you need to completely reset the device here are some recommendations:
1. Charge the battery by leaving the phone plugged for a while (even in bootloop)
2. Try to hard restart the device by holding `POWER` for ~10 seconds
3. Try to make a userdata backup using `mtkclient` BROM exploit
4. Try to boot into fastboot or recovery mode via key combo (or by plugging the phone and only with volume key if it bootloops)
    - recovery: `POWER` + `VOLUME UP`
    - fastboot: `POWER` + `VOLUME DOWN`
5. From recovery: Wipe Data  **!! this will format userdata and erase all your data from the phone !!**
6. From fastboot:
    - dirty flash the same system image (data should be preserved)
    - format data: `fastboot -w`
    - clean flash a system image
7. Use SP Flash Tool and bypass utility: see [postmarketOS unbrick guide](https://wiki.postmarketos.org/wiki/Xiaomi_Redmi_Note_8_Pro_(xiaomi-begonia)#Unbricking)

## Testers

| What | Value |
|-|-|
| Tester | [BZORG](https://github.com/BZ0RG) |
| Vendor | `V12.5.15.0.RGGEUXM` |
| Kernel | `4.14.186-g4e5507d5edae` and `4.14.329-NoVa-KSU` |
| Features not tested | Double SIM / VoLTE / NFC payment |
| TrebleDroid | [android_14.0.0_r27 ci-20240226](https://github.com/TrebleDroid/treble_experimentations/releases/tag/ci-20240226) ✔ |
| QPR2 | [android_14.0.0_r29 ci-20240401](https://github.com/TrebleDroid/treble_experimentations/releases/tag/ci-20240401) ❌ |

Thanks to previous testers [hopefullyidontgetbanned](https://github.com/timbortnik), [tvardero](https://github.com/tvardero) and [timbortnik](https://github.com/Hopefullyidontgetbanned) on early stages of GSI testing (May 2020).