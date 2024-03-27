# [Nokia X100] - [deadmau5 / DM5]

Bootloader Unlock : Not easily doable by average users.

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

This phone is carrier locked to T-Mobile USA, the telephony related functionalites cannot be tested.

## Tested By:

@HikariCalyx @ Nokia G100 04US_1_440 @ 03/27/2024


Template created by @zguithues