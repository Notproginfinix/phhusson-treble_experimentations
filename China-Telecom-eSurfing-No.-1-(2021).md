# [China Telecom eSurfing No. 1 (2021)] - [AURORA]

Bootloader Unlock : Generic Unisoc Bootloader method involves SpreadtrumTools can be used.
## Hardware Support (Android 12)

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | √                                                         |
| Speaker / Mic             | √                                                         |
| Bluetooth                 | √                                                         |
| WiFi                      | √                                                         |
| SIM / Mobile Data / Voice | √                                                         |
| VoLTE                     | ×                                                         |
| Fingerprint               | √                                                         |
| 5G                        | √                                                         |

## Additional Notes

To enable 5G, you'll need to configure "NR" in preferred network type.

To install a GSI, you need to modify the fstab.ud710_7h10 inside of /vendor/etc to disable the encryption. 
```
fastboot flash vendor /path/to/your/modified/vendor.img
fastboot flash system /path/to/your/gsi/image.img
fastboot reboot-recovery
```
Then, choose wipe data / factory reset and reboot immediately.

## Tested By:

@HikariCalyx @ China Telecom eSurfing No. 1 (2021) Zhenqing TYH211U 1.8.1 @ 11/08/2024

Template created by @zguithues