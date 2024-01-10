## Steps to install

* Unlock Bootloader
* Patch and Flash recovery with fastbootd (you can patch recovery with https://github.com/Johx22/Patch-Recovery)
* Boot into recovery and enable fastbootd
* Flash arm64 GSI with fastboot
* Wipe Data and Cache
* Reboot

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Working (Only Front Main and Back Cameras)                |
| Speaker / Mic             | Working                                                   |
| Bluetooth                 | Working                                                   |
| WiFi                      | Working                                                   |
| SIM / Mobile Data / Voice | Working (cannot send SMS on Android 14, but works in 13)  |
| VoLTE                     | Not Working                                               |
| Fingerprint               | Working                                                   |
| NFC                       | Working                                                   |
| Offline Charging          | Not Tested                                                |
| 5G                        | Not Working                                               |
---

Tested by @ootrey with Galaxy S20 5G (SM-G9810)