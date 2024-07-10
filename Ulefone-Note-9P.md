# Ulefone Note 9P

## Hardware support

| Component                 |      Comment                                          |
|---------------------------|-------------------------------------------------------|
| Camera                    | OK.                                                   |
| Speaker / Mic             | OK (mic not tested)                                   |
| Bluetooth                 | OK (activates, but not tested)                        |
| WiFi                      | OK                                                    |
| SIM / Mobile Data / Voice | not tested                                            |
| VoLTE                     | not tested                                            |
| Fingerprint               | not tested                                            |
| NFC                       | not tested                                            |
| Offline Charging          | not tested                                            |

Image tested: https://github.com/TrebleDroid/treble_experimentations/releases/tag/ci-20240226

Enable Developer mode, enable oem unlock in developer settings. Reboot to fastboot and in the appropriate fastboot/recovery mode only these commands are necessary, nothing else at all.
```
fastboot flashing unlock
fastboot erase system
fastboot flash system system-td-arm64-ab-vanilla.img
```

---
Tested By: @ChristophHaag - Date tested: 2024-07-10 - Template created by @zguithues and @hackintosh5
