# [China Telecom eSurfing No. 1 (2022) / Zhenqing] - [TYH212U]

Bootloader Unlock : Generic Unisoc Bootloader method involves SpreadtrumTools can be used.
## Hardware Support (Android 14)

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

Brightness is significantly lower than stock OS.
To enable 5G, you'll need to configure "NR" in preferred network type.

To install a GSI, the phone must enter fastbootd and execute these commands:
```
fastboot delete-logical-partition system_a-cow
fastboot delete-logical-partition system_ext_a-cow
fastboot delete-logical-partition product_a-cow
fastboot delete-logical-partition vendor_a-cow
fastboot flash system_a /path/to/your/gsi/image.img
fastboot reboot-recovery
```
Then, choose wipe data / factory reset and reboot immediately.

## Tested By:

@HikariCalyx @ China Telecom eSurfing No. 1 (2022) Zhenqing TYH11.7.0.0Q @ 02/06/2024

Template created by @zguithues