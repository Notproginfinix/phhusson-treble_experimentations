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
* From the command-line, type `fastboot reboot recovery` to wipe data.
* Reboot.

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Working                                                   |
| Speaker / Mic             | Working                                                   |
| Headphones                | Working                                                   |
| Bluetooth                 | Working                                                   |
| WiFi                      | Working                                                   |
| SIM / Mobile Data / Voice | Working                                                   |
| VoLTE                     | Working                                                   |
| Fingerprint               | Working                                                   |
| Offline Charging          | Working                                                   |
| NFC                       | N/A                                                       |


## References
Template created by @zguithues and @hackintosh5