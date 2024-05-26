# General Mobile GM 24 Pro (G514 / G515)

- Mostly all of the features work, except fingerprint. Needs to be worked on
- This device *might* also be "NUU A25" and "DCODE Bold 3 Pro"

## Device properties

![General Mobile GM 24 Pro](https://assets.generalmobile.com/images/gm24pro-7f8b8b30/s1-img-mobile.png.webp)
Basic   | Spec Sheet
-------:|:-------------------------
CPU     | 2x 2.2 GHz ARM Cortex-A76 + 6x 2.0 GHz ARM Cortex-A55
CHIPSET | Mediatek Helio G99 (MT6789)
GPU     | Mali-G57 MC2
Memory  | 8 GB
Shipped Android Version | 13
Storage | 256GB
MicroSD | Up to 1TB
Battery | 5000 mAh (non-removable)
Display | 1080 x 2142, 6.7" AMOLED
Rear Camera  | 50.0MP + 2.0MP + 0.08MP
Front Camera | 16.0MP
Release Date | August 2023


## Steps to install

* Boot into fastboot (Note: After selecting "fastboot mode", there's no visual signal that you're in fastboot. Make sure you verify it by running `fastboot devices`

* Flash stock (or empty) vbmeta using this command:
    ```
    $ fastboot --disable-verity --disable verification vbmeta_a vbmeta.img
    $ fastboot --disable-verity --disable verification vbmeta_b vbmeta.img
    ```

* Reboot to fastbootd
    ```
    $ fastboot reboot fastboot
    ```

* Flash system (you might have to delete the product and/or system_a-cow partition to flash large images)
    ```
    $ fastboot flash system system_arm64-vanilla.img
    ```

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Working                                                   |
| Speaker / Mic             | Working                                                   |
| Bluetooth                 | Not tested                                                |
| WiFi                      | Working                                                   |
| SIM / Mobile Data / Voice | Working                                                   |
| VoLTE                     | Working                                                   |
| Fingerprint               | Not working                                               |
| NFC                       | Not tested                                                |
| Offline Charging          | Working                                                   |
---

## Resources
| Resource    | Link | By |
|-------------|------|----|
| **STOCK ROM** | To be uploaded| loongruige |
| Dark logo   | [logo_final.bin](https://cdn.discordapp.com/attachments/1227287601560424448/1244252092743290911/logo_final.bin?ex=66546f8f&is=66531e0f&hm=ab6a70cfa81afe712673bea6b5a38d2f88e5fad74bbf2d3acf8adbb3802f2caa&) | loongruige |
| Patched LK (with delay) | [lk_a.bin](https://cdn.discordapp.com/attachments/1227287601560424448/1244252170317074452/lk_a.bin?ex=66546fa2&is=66531e22&hm=dbb79089af5f12d86b6d65e4a3d2e0e8a458dce7972b27057fd55efe88a72e4c&) | loongruige |

Tested By: [loongruige](https://github.com/loongruige) - G514, Android 13 - May 2024