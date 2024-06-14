# [Nokia G300] - [aoki / AKT]

Bootloader Unlock : 
First it cannot be easily done by average person. 

Then, bootloader unlock is only possible with firmware 02US_1_10M or older, where "AntiRollback" returned from "fastboot oem get_devinfo" should be 2.

If newer than 02US_1_10M, then the "AntiRollback" is 3, which bootloader unlock will not be possible. Attempting bootloader unlock on such device will hard brick the phone.

## Hardware Support (Android 14)

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | ?                                                         |
| Speaker / Mic             | ?                                                         |
| Bluetooth                 | ?                                                         |
| WiFi                      | ?                                                         |
| NFC                       | ?                                                         |
| SIM / Mobile Data / Voice | ?                                                         |
| VoLTE                     | ?                                                         |
| Fingerprint               | ?                                                         |
| 5G                        | ?                                                         |


## Additional Notes

You'll need to delete product and system_ext partitions under fastbootd before flashing GSI:
```
fastboot delete-logical-partition product_a
fastboot delete-logical-partition system_ext_a
```

## Tested By:

@HikariCalyx @ Nokia G300 02US_1_10M @ 14/06/2024


Template created by @zguithues