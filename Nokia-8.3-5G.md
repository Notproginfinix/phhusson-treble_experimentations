# [Nokia 8.3 5G] - [BabyGroot / BGT]

Bootloader Unlock : https://forum.xda-developers.com/t/guide-how-to-unlock-the-bootloader-for-nokia-8-3-5g.4233949/

Nokia 8V 5G UW users need to use different prototype ABL image to unlock the bootloader and allow partition flashing.

## Hardware Support (Android 11)

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | √                                                         |
| Speaker / Mic             | √                                                         |
| Bluetooth                 | √                                                         |
| WiFi                      | √                                                         |
| NFC                       | √                                                         |
| SIM / Mobile Data / Voice | √                                                         |
| VoLTE                     | ×                                                         |
| Fingerprint               | √                                                         |
| 5G                        | √                                                         |

## Hardware Support (Android 11, Nokia 8V 5G UW)

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | √                                                         |
| Speaker / Mic             | √                                                         |
| Bluetooth                 | √                                                         |
| WiFi                      | √                                                         |
| NFC                       | √                                                         |
| SIM / Mobile Data / Voice | ?                                                         |
| VoLTE                     | ?                                                         |
| Fingerprint               | √                                                         |
| 5G                        | ?                                                         |

## Additional Notes

To enable 5G, you'll need to configure "NR" in preferred network type.

For Nokia 8V 5G UW, to enter Fastbootd you must execute: ```adb shell reboot fastboot```

We recommend you to install latest stock firmware (00VPO_1_45H) before installing GSI, so you won't be blocked away from unable to accept flashing commands.

## Tested By:

@HikariCalyx @ Nokia 8.3 5G 00WW_1_150 (BGT-1150-0-00WW-B01) @ 19/01/2021

@HikariCalyx @ Nokia 8V 5G UW 00VPO_1_45H (RAV-145H-0-00VPO-B01) @ 14/07/2023

Template created by @zguithues