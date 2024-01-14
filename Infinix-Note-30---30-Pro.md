## Installation Steps

### Disable VBMETA

You have two options for disabling VBMETA:

1. **Using Fastboot:**
    - Boot into the bootloader and flash [vbmeta.img](https://t.me/infinixnote30indonesia/125898) using the following command:
        ```bash
        fastboot --disable-verification --disable-verity flash vbmeta vbmeta.img
        ```

2. **Using Recovery (TWRP/OrangeFox):**
    - Flash [FLASH_DISABLE_VBMETA.zip](https://t.me/infinixnote30indonesia/135864) in recovery.

### Flashing Generic System Image (GSI)

1. With [TWRP terminal](https://telegra.ph/Terminal-TWRP-08-01):

    - Ensure your current system is in slot _a.
    - Execute the following commands:
    ```bash
    lptools resize product_a 335872 # Do not change this value
    lptools resize system_a 4617089843 # or 5368709120 (4.3GB or 5GB system)
    ```

    - Reboot to recovery.
    - Flash [product_gsi.img](https://t.me/UdgUpdates/46) to the [product partition](https://telegra.ph/Product-img-07-31).
    - Install GSI to the [system partition](https://telegra.ph/System-img-07-31).
    - Format DATA.
    - Reboot the system.

2. Using latest custom recovery with logical partition flash fix

    - Reboot to fastbootd
    - Execute the following commands:
    ```bash
    fastboot flash product_a product_gsi.img
    fastboot flash system_a GSI.img
    fastboot erase userdata
    fastboot erase metadata
    ```
    - Reboot the system.

### Hardware Support

| Component                 | Comment                                                  |
|---------------------------|----------------------------------------------------------|
| Camera                    | Works                                                    |
| Speaker / Mic             | Works                                                    |
| Headphone                 | Works with "module"                                       |
| USB DAC                   | Works                                                    |
| USB OTG                   | Works with "module"                                       |
| GPS                       | Works                                                    |
| Bluetooth                 | Works                                                    |
| NFC                       | Works                                                    |
| WiFi                      | Works                                                    |
| SIM / Mobile Data / Voice | Works                                                    |
| Tethering                 | Works                                                    |
| Proximity Sensor          | Works                                                    |
| Accelerometer / Gyroscope | Works                                                    |
| VoLTE                     | Works with "IMS features / Install IMS APK for MediaTek S vendor / |
|                           | Force presence of 4G calling / Re-toggle VoLTE in SIM settings" |
| RCS Message               | Works                                                    |
| Fingerprint               | Works                                                    |
| Brightness                | Works                                                    |
| Auto Brightness           | Works with "module"                                       |
| Offline Charging          | Works                                                    |
| Fast Charging             | Works                                                    |
| Display Refreshing Rate   | Supports 60/90/120Hz with "Misc features / Force FPS"      |
| Double Tap To Wake Up (dt2w)  | Works                                                    |
| Vibration                 | Works                                                    |

### Tweaks and Fixes

[Module GSI Infinix Note 30/Pro v2.5](https://github.com/phhusson/treble_experimentations/files/13931320/modulegsi-infinixnote30all_v2.5.zip)
1. Fix Smoothness
2. Fix StatusBar
3. Fix Brightness X6883B (Note 30)
4. Fix auto brightness
5. Fix Clock position in statusbar
6. Fix USB OTG

Use as a Magisk/KSU module.

---

**Tested By:**
- Deca1708 - Infinix Note 30 - TrebleDroid Android 14
- rama982 - Infinix Note 30 Pro - TrebleDroid Android 14
