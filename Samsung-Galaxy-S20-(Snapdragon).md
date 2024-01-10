## Steps to install

* Unlock Bootloader
* Download the latest stock [firmware](https://samfw.com/)
* Patch stock recovery with [Patch-Recovery](https://github.com/Johx22/Patch-Recovery) and flash it through Odin
* Flash arm64 GSI with fastboot. (Detailed instructions can be found on [XDA](https://xdaforums.com/t/full-definitive-guide-installing-custom-roms-gsis-without-twrp-on-samsung-phones.4551963/))
* Reboot

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Working (Only Front Main and Back Cameras)                |
| Speaker / Mic             | Working                                                   |
| Bluetooth                 | Working                                                   |
| WiFi                      | Working                                                   |
| SIM / Mobile Data / Voice | Working (Cannot send [SMS](https://github.com/TrebleDroid/treble_experimentations/issues/62) on Android 14)                   |
| VoLTE                     | Not Working                                               |
| Fingerprint               | Working                                                   |
| NFC                       | Working                                                   |
| Offline Charging          | Not Tested                                                |
| 5G                        | Not Working                                               |
---

Tested by [@ootrey](https://github.com/ootrey) with Galaxy S20 5G (SM-G9810)