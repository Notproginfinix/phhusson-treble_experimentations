# [Nokia 2.3] - [ironman / IRM]

Bootloader Unlock : 

Please use [MTKClient](https://github.com/bkerler/mtkclient) to perform bootloader unlock.

To remove your device is corrupt warning, simply flash vbmeta image and disable verity/verification.

## Hardware Support (Android 13)

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | ✓                                                         |
| Speaker / Mic             | ✓                                                         |
| Bluetooth                 | ✓                                                         |
| WiFi                      | ✓                                                         |
| SIM / Mobile Data / Voice | ✓                                                         |
| VoLTE                     | ✓                                                         |


## Additional Notes

Tested GSI: [system-td-arm32_binder64-ab-vanilla.img.xz](https://github.com/TrebleDroid/treble_experimentations/releases/download/ci-20230706/system-td-arm32_binder64-ab-vanilla.img.xz)

```
fastboot flash system /path/to/gsi/image.img
fastboot --disable-verity --disable-verification flash vbmeta /path/to/vbmeta.img
```

~~After flashing it along with vbmeta, you must format userdata partition as f2fs filesystem, or the phone will bootloop~~

Delete keystore* files from /vendor/lib/hw/ or it won't boot

## Tested By:
@pcurz @ Nokia 2.3 TA-1214 00WW_3_310_SP09 (IRM-331J-0-00WW-B01) @ 14/07/2023

@HikariCalyx @ Nokia 2.3 TA-1206 00WW_3_310_SP09 (IRM-331J-0-00WW-B01) @ 02/04/2023

Template created by @zguithues