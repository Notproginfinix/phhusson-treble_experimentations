# 📱 Xiaomi POCO X4 GT - xaga


## Tested images
[LineageOS 21 (2024-09-18) Signed + GAPPS](https://sourceforge.net/projects/andyyan-gsi/files/lineage-21-td/lineage-21.0-20240918-UNOFFICIAL-arm64_bgN-signed.img.gz/download)

Working fine, but there are some minor bugs.

Magisk root and LSPosed works.

## 📃 Steps to install
1. Unlock bootloader
2. Enter bootloader and flash latest stock HyperOS. This step is important, you will encounter bugs otherwise!
3. Disable secure boot by flashing vbmeta_system.
4. Now boot into fastbootD then delete product_a and product_b partitions.
5. Flash system partition
6. Wipe and reboot your phone

## 📃 Command cheat sheet
```sh
fastboot flash --disable-verity --disable-verification vbmeta_system_ab vbmeta_system.img
fastboot reboot fastboot
fastboot erase system
fastboot delete-logical-partition product_a
fastboot delete-logical-partition product_b
fastboot flash system system.img
fastboot -w reboot
```

## ⚙️ Hardware support

| Component                 | Status |      Comment                                                |
|---------------------------|--------|-------------------------------------------------------------|
| Camera                    | ✅     |      Works                                                  |
| Speaker / Mic             | ⚠️     |      Works but see issues below                             |
| SIM / Mobile Data / Voice | ✅     |      Works but without MMS                                  |
| IMS                       | ✅     |      Works                                                  |
| WiFi                      | ✅     |      Works                                                  |
| Bluetooth                 | ✅     |      Works                                                  |
| Fingerprint               | ✅     |      Works                                                  |
| Jack                      | ✅     |      Works                                                  |
| NFC                       | ✅     |      Works                                                  |
| 144 Hz display            | ✅     |      Works                                                  |
| IR                        | ✅     |      Works                                                  |
| Sensors                   | ✅     |      Works                                                  |

## ⚠️ Known issues and solutions
- **First of all open phh treble settings and examine each option. If properly configured, it solves 90% of all bugs.**
- Camera sometimes throws fatal error and OpenCamera apk hangs. Just close it and reopen.
- Speaker requires calibration for stereo playback. I'm using Precise Volume apk and it solves the issue.
- Speaker is sometimes too loud during phone call and it's impossible to turn down the volume. Reboot solves the issue.
- Mobile Data hangs on 3G despite of 4G and 5G availability. Enable airplane mode and turn it off after few seconds.
- Bluetooth crashes while connecting to the speaker. It's vendor issue - just flash latest HyperOS.
- Video hangs (in NewPipe apk for example). It's another vendor issue - fix same as above.
- GUI crashes to lock screen. Just enter your pin again or unlock using fingerprint sensor.