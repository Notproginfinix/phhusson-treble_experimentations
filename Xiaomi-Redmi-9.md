# Xiaomi Redmi 9 (lancelot/galahad)

![](https://wiki.lineageos.org/images/devices/lancelot.png)

## Requirements

1. PC with ```ADB``` and ```fastboot``` drivers installed.
2. Unlock bootloader with [Mi Unlock](https://en.miui.com/unlock/index.html) or using [MTK Client](https://github.com/bkerler/mtkclient).
3. Flash the latest MIUI firmware: [mirror 1](https://cdnorg.d.miui.com/V13.0.4.0.SJCMIXM/lancelot_global_images_V13.0.4.0.SJCMIXM_20230111.0000.00_12.0_global_06d1b1156a.tgz), [mirror 2](https://bkt-sgp-miui-ota-update-alisgp.oss-ap-southeast-1.aliyuncs.com/V13.0.4.0.SJCMIXM/lancelot_global_images_V13.0.4.0.SJCMIXM_20230111.0000.00_12.0_global_06d1b1156a.tgz), [mirror 3](https://bn.d.miui.com/V13.0.4.0.SJCMIXM/lancelot_global_images_V13.0.4.0.SJCMIXM_20230111.0000.00_12.0_global_06d1b1156a.tgz), [mirror 4](https://bigota.d.miui.com/V13.0.4.0.SJCMIXM/lancelot_global_images_V13.0.4.0.SJCMIXM_20230111.0000.00_12.0_global_06d1b1156a.tgz), [mirror 5](https://hugeota.d.miui.com/V13.0.4.0.SJCMIXM/lancelot_global_images_V13.0.4.0.SJCMIXM_20230111.0000.00_12.0_global_06d1b1156a.tgz).
4. ```vbmeta.img```, can be obtained from the extracted MIUI firmware, it can be found in the ___images___ folder.

## Download GSIs

1. Download from [Generic System Image (GSI) list](https://github.com/phhusson/treble_experimentations/wiki/Generic-System-Image-%28GSI%29-list) .
2. Extract ```.xz``` to ```.img```

## Install a GSI

1. Boot into fastboot mode.

``````
adb reboot bootloader
``````

> Or via key combination: hold ```Volume Down``` + ```Power``` while the device is turned off.

2. Disable verified boot.

``````
fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
``````

3. Moving fastboot from bootloader to userspace (fastbootd)

``````
fastboot reboot fastboot
``````

4. Flash the GSI.

``````
fastboot flash system system.img
``````

> Note: ___system.img___ is the extracted GSI e.g ___system-td-arm64-ab-vanilla.img___.

5. Wipe data from MIUI recovery.

``````
fastboot reboot recovery
``````

> Choose ```Wipe Data``` → ```Wipe All Data``` → ```Confirm```

6. Reboot.

> Return to the main menu Recovery → ```Reboot``` → ```Reboot to System```

## Update a GSI

1. Enter fastboot in userspace (fastbootd).

``````
adb reboot fastboot
``````

2. Flash the GSI.

``````
fastboot flash system system.img
``````

> Note: ___system.img___ is the extracted GSI e.g ___system-td-arm64-ab-vanilla.img___.

3. Reboot

``````
fastboot reboot
``````

> Note: No need to wipe data as long as the image is the same e.g ```AOSP to AOSP``` or ```LineageOS TD-based to LineageOS TD-based``` ******NOT****** ```AOSP to LineageOS TD-based``` or vice versa.

## Hardware support

|Component                 |Comment |
|--------------------------|--------|
|Audio                     |Working |                                         
|Display                   |Working |
|Backlight                 |Working → Enable ```Force alternative backlight scale``` to fix brightness slider|
|Camera                    |Working → Auxiliary cameras doesn't work |
|Bluetooth                 |Working → Choose ```Bluetooth workarounds``` → ```Mediatek```|
|Telephony                 |Working |
|Fingerprint               |Working |
|VoLTE                     |Working → Enable IMS features|


## Additional information

* Q: Do you have to enable `Rotation perf hint instead of touch`, `Mediatek GED KPI support` and/or `Disable SF GL backpressure` ?
* A: No

I've done `3DMark` & `Geekbench 6` benchmarks, here are the results:

**3DMark (Vulkan)**

|Preferences                                       |Enabled|Scores|
|--------------------------------------------------|-------|------|
|Rotation perf hint instead of touch               |Yes    |671   |
|Mediatek GED KPI support                          |Yes    |672   |
|Disable SF GL backpressure                        |Yes    |668   |
|The 3 options above                               |No     |674   |

**Geekbench CPU**

|Preferences                                       |Enabled|Single-Core Scores|Multi-Core Scores|
|--------------------------------------------------|-------|------------------|-----------------|
|Rotation perf hint instead of touch               |Yes    |415               |1365             |
|Mediatek GED KPI support                          |Yes    |416               |1363             |
|Disable SF GL backpressure                        |Yes    |414               |1374             |
|The 3 options above                               |No     |414               |1379             |

**Geekbench GPU (OpenCL)**

|Preferences                                       |Enabled|Scores|
|--------------------------------------------------|-------|------|
|Rotation perf hint instead of touch               |Yes    |1110  |
|Mediatek GED KPI support                          |Yes    |1112  |
|Disable SF GL backpressure                        |Yes    |1109  |
|The 3 options above                               |No     |1116  |

**Geekbench GPU (Vulkan)**

|Preferences                                       |Enabled|Scores|
|--------------------------------------------------|-------|------|
|Rotation perf hint instead of touch               |Yes    |1080  |
|Mediatek GED KPI support                          |Yes    |1084  |
|Disable SF GL backpressure                        |Yes    |1076  |
|The 3 options above                               |No     |1090  |

_Note: Reboot is performed before benchmarking in each session_

## Credits
* TrebleDroid developer team for all their hard work.
* All contributors for their respective contributions.