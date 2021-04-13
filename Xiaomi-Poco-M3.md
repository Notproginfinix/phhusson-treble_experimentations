# Xiaomi Poco M3 (Global)

Tested with image `system-roar-arm64-ab-gapps.img (v303)`. Most features work well.
- `Bluetooth: audio 🎵` doesn't work.
- `Multiuser` and some apps might not fully compatible.

## Steps to Install

[**DISCLAIMER: READ THIS LINK BEFORE AND USE AT YOUR OWN RISK!**](https://android.stackexchange.com/a/21054)

* **BACKUP EVERYTHING** you can!
* Unlock your `bootloader`
* Install `TWRP` or `OrangeFox`
* Again, **BACKUP EVERYTHING** you can!!
* Boot to the non-original `fastboot` mode
* Download and extract the selected image from the [release page](https://github.com/phhusson/treble_experimentations/releases)
* Flash this image with the `fastboot` utility:
    ```
    $ fastboot flash system system-<version>-arm64-<variants>.img
    ```

## Hardware Support

| Component                 | Comment                                                   |
|---------------------------|-----------------------------------------------------------|
| Camera                    | ✅                                                        |
| Speaker / Mic             | ✅ Loud Speaker (Stereo);  ✅ Ear Speaker; ✅ Mic          |
| Bluetooth                 | ✅ Pairing; ✅ File Sharing; ❌ Audio; ❓ Mic              |
| WiFi                      | ✅                                                        |
| SIM / Mobile Data / Voice | ✅ (Tested /w 4G); ✅ SMS                                 |
| VoLTE                     | ❓                                                        |
| Fingerprint               | ✅                                                        |
| NFC                       | N/A                                                       |
| Offline Charging          | ✅                                                        |
| GPS                       | ✅                                                        |
| IR                        | ✅                                                        |
| Other feature(s)          | ✅ 3.5 headset audio and mic and button jack (TRRS)       |
|                           | ✅ Portable storage: SD card                              |

## System Features / Apps Compatibilities

| Target                    | Comment                                                   |
|---------------------------|-----------------------------------------------------------|
| System: Multiuser         | ✅ See [issue #1794](https://github.com/phhusson/treble_experimentations/issues/1794) for GApps ROM |
| System: Live Wallpaper    | ✅ Lock and Home                                          |
| System: Screen Recording  | ❗️ Lags                                                   |
| Magisk                    | ✅ Root                                                   |
| Youtube Vanced            | ❗️ Rooted only; Needs reinstall after reboot.             |
| YT Music (Also Vanced)    | ❗️ Rooted only; Needs reinstall after reboot.             |
| Storage Isolation         | ❌                                                        |
| microG                    | ❌                                                        |

---
Tested By: [@edwining01](https://github.com/edwining01) - M2010J19CG(HK) - 20210407 - Template created by @zguithues and @hackintosh5