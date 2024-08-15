# Alldocube iPlay50 Pro (T1030M)

Installation instructions and tests

## Steps to install
### unlock the bootloader
`fastboot flashing unlock`

### Flashing
`adb reboot fastboot`

reboot to fastboot, not to the bootloader

`fastboot flash system_a crDroid-8.13-arm64_bgN-slim-Unofficial.img`

Don't forget to do a factory reset.

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    |Works|
| Speaker / Mic / Calls     |Works|
| Bluetooth                 |Works|
| WiFi                      |Works|
| SIM / Mobile Data / Voice |Not tested|
| VoLTE                     |Not tested|
| Fingerprint               |No fingerprint hardware|
| NFC                       |No NFC hardware|
| USB              |Works|
| Accelerometers and other sensors                       |Works|
| FM Radio              |Malfunctions (*)|
| GPS              |Works|
| Play Integrity             |MEETS_BASIC_INTEGRITY|


---
*Unlike custom roms built and finely polished from open source code, there is no built-in FM radio software in generic system images. So you need to find one from somewhere else. This requires a lot of luck, and it's very likely that the FM radio software you find won't work!

## Tested by
 @Cyanide-zh - iPlay50Pro(T1030M)-Android12-20221223 base [[crDroid-8.13-arm64_bgN-slim-Unofficial.img.xz](https://sourceforge.net/projects/gsi-projects/files/A12.1/crDroid-8.10/v-8.13/21012023/crDroid-8.13-arm64_bgN-slim-Unofficial.img.xz/download)] - Tested 2023-07-12

_Template created by @zguithues and @hackintosh5_