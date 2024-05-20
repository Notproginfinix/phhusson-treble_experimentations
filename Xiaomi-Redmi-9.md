# Xiaomi Redmi 9

## Requirements
* PC with ADB/Fastboot drivers installed.
* Unlock bootloader with https://en.miui.com/unlock/index.html or using https://github.com/bkerler/mtkclient
* Flash latest MIUI firmware https://xiaomifirmwareupdater.com/miui/lancelot/stable/V13.0.4.0.SJCMIXM/ (fastboot version is recommended).
* vbmeta.img (can be obtained from the extracted MIUI firmware).

## Download GSIs
* Download from [Generic System Image (GSI) list](https://github.com/phhusson/treble_experimentations/wiki/Generic-System-Image-%28GSI%29-list) .
* Extract.

## Install a GSI
* From the command-line, type `adb reboot bootloader` to boot into Fastboot mode.
* From the command-line, type `fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img` to disable verified boot.
* From the command-line, type `fastboot reboot fastboot` to move Fastboot from bootloader to userspace.
* From the command-line, type `fastboot flash system system.img` to flash the GSI (_system.img_ is the extracted GSI e.g _system-td-arm64-ab-vanilla.img_).
* From the command-line, type `fastboot reboot recovery` to wipe data from MIUI recovery.
* Reboot.

## Hardware support
|Component                 |Comment |
|--------------------------|--------|
|Audio                     |Working |                                         
|Display                   |Working |
|Backlight                 |Working |
|Camera                    |Working |
|Bluetooth                 |Working |
|Telephony                 |Working |
|Fingerprint               |Working |
|VoLTE                     |Working |


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