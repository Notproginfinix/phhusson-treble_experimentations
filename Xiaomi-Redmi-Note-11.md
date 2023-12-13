# Tested images

Mostly working fine (see Hardware support bellow)

- [TrebleDroid's AOSP android_14.0.0_r17: `system-td-arm64-ab-vndklite-vanilla.img`](https://github.com/TrebleDroid/treble_experimentations/releases/tag/android_14.0.0_r17)
- [AndyYan's unnoficial LineageOS 20: `lineage-20.0-20231116-UNOFFICIAL-arm64_bvN.img`](https://sourceforge.net/projects/andyyan-gsi/files/lineage-20-light/)

# Steps to install

```
unxz your_gsi_rom_of_choice.img.xz

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
unxz your_gsi_rom_of_choice.img.xz

fastboot reboot fastboot
fastboot flash system your_gsi_rom_of_choice.img
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