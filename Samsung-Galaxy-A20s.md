# Device

Summary of what works and doesn't

## Steps to install

* Follow this guide : https://forum.xda-developers.com/t/guide-twrp-root-how-to-install-twrp-and-root-on-a20s-sm-a207f.4293965/ till the flashing GSI Steps. TWRP cannot be installed on this device. **(DO NOT try the Odin flashing method, as you will end up with a "U5->U0 Downgrade" error)**

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Works                                                     |
| Speaker / Mic             | Works                                                     |
| Bluetooth                 | Works (and BT Audio works too)                            |
| WiFi                      | Works                                                     |
| SIM / Mobile Data / Voice | Works                                                     |
| VoLTE                     | Not Supported                                             |
| Fingerprint               | Works                                                     |
| NFC                       | Not Present in Device                                     |
| Offline Charging          | Untested                                                  |
| Fast Charging             | Doesn't work                                              |
| Screen mirroring (Cast)   | Doesn't work                                              |
| SD Card                   | Works                                                     |
| MTP (Connection to PC via Cable) and other connection modes | Doesn't work                             |
| Other feature             | To be tested                                              |
---

Tested By: **InsertX2k** - On **SM-A207F/DS(EGY)**, Build Number - **A207FXXS5CWF1**

GSI Tested: [android_13.0.0_r73 ci-20230905 - TrebleDroid](https://github.com/TrebleDroid/treble_experimentations/releases/tag/ci-20230905) (file: **system-td-arm64-ab-vndklite-vanilla.img.xz**)