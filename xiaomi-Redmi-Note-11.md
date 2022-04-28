
# Tested images

- PixelExperience_arm64-ab-vndklite-12.1-20220329-UNOFFICIAL

# Steps to install

```
fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
fastboot reboot fastboot
fastboot flash system your_gsi_rom_of_choice.img
fastboot -w
```


# Hardware Support post flashing

| Component | Comment|
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
