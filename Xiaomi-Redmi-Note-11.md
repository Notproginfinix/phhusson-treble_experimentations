# Tested images

Mostly working fine (see Hardware support bellow)

- [AndyYan's unnoficial LineageOS 21 (TD-based): `lineage-21.0-20241018-UNOFFICIAL-arm64_bvN.img.gz`](https://sourceforge.net/projects/andyyan-gsi/files/lineage-21-td/)
- [AndyYan's unnoficial LineageOS 20 ("Light"): `lineage-20.0-20231116-UNOFFICIAL-arm64_bvN.img`](https://sourceforge.net/projects/andyyan-gsi/files/lineage-20-light/)
- [TrebleDroid's AOSP android_14.0.0_r17: `system-td-arm64-ab-vndklite-vanilla.img`](https://github.com/TrebleDroid/treble_experimentations/releases/tag/android_14.0.0_r17)

# Preparation

Download the [SDK Platform Tools](https://developer.android.com/tools/releases/platform-tools).

Download and uncompress the image file:

```
# For `.gz` compressed files
gzip -d your_gsi_rom_of_choice.gz

# For `.xz` compressed files
unxz your_gsi_rom_of_choice.img.xz
```

# Steps to install

```
# Flasb vbmeta
wget https://dl.google.com/developers/android/qt/images/gsi/vbmeta.img
fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img

# Enter fastbootd
fastboot reboot fastboot  # If this does not work: boot system and `adb reboot fastboot`

# Flash system and wipe userdata
fastboot flash system your_gsi_rom_of_choice.img
fastboot -w  # Wipe userdata
fastboot reboot
```

# Steps to update (if OTA is not working)

```
# Enter fastbootd
fastboot reboot fastboot  # If this does not work: boot system and `adb reboot fastboot`

# Flash system
fastboot flash system your_gsi_rom_of_choice.img
fastboot reboot
```

# Hardware Support post flashing

| Component | Comment |
| --- | --- |
| Camera | Works |
| Speaker/Mic | Works (headphone jack requires [tweak](#notes)) |
| Bluetooth | Works |
| Wi-Fi | Works |
| SIM/Mobile Data/Voice | Works |
| VoLTE | Not tested |
| Fingerprint | Works |
| NFC | Works |
| Offline Charging | Not tested |
| Display Refresh rate | 60Hz (90Hz in phh settings) |
| Screen Brightness | Works (but auto-brightness is weird sometimes) |
| Volume scale | Works |
| 5G | N/A |
| SafetyNet post root | Passed (with safetynet-fix in magisk) |
| WideVine certification post flash and root | L1 |

# Notes

- For headphone jack enable `Qualcomm > Use alternate audio policy`