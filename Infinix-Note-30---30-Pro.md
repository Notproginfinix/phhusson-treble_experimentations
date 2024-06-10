# Infinix Note 30/30 Pro (X6883B/X678B)

Works as expected.

## Steps to install

WARNING: This guide assumes that you are using the A slot instead of the B slot. To move to the A slot, use `fastboot set_active a`, flash super.img from firmware and reboot, or you can use the B slot by replacing all the "_a" suffix to "_b" suffix.

* Unlock bootloader
* Disable VBMETA
    ```
    fastboot --disable-verification --disable-verity flash vbmeta vbmeta.img
    ```
* Enter fastboot
    ```
    adb reboot fastboot
    ```
    or
    ```
    fastboot reboot fastboot
    ```
* Remove or resize product and system_ext partitions (optional, but highly recommended since they take a large amount of space)
    ```
    fastboot delete-logical-partition product_a
    fastboot delete-logical-partition system_ext_a
    ```
    or resize it by doing the following
    ```
    fastboot resize-logical-partition product_a 335872
    fastboot resize-logical-partition system_ext_a 335872
    fastboot format:ext4 product_a
    fastboot format:ext4 system_ext_a
    ```
* Flash the GSI
    ```
    fastboot flash system_a system-ab-gsi.img
    ```
* Wipe data
    ```
    fastboot -w
    ```
* Reboot the device

<details><summary>Flash using TWRP instead</summary>

### Disable VBMETA

**Using Recovery (TWRP/OrangeFox):**

- Flash [FLASH_DISABLE_VBMETA.zip](https://t.me/infinixnote30indonesia/135864) in recovery.

### Flashing Generic System Image (GSI)

With [TWRP terminal](https://telegra.ph/Terminal-TWRP-08-01):

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

</details>

### Hardware Support

| Component                 | Comment                                                  |
|---------------------------|----------------------------------------------------------|
| Camera                    | Works                                                    |
| Speaker / Mic             | Works                                                    |
| Headphone                 | Works                                                    |
| USB DAC                   | Works                                                    |
| USB OTG                   | Works                                                    |
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
| Auto Brightness           | Works                                                    |
| Offline Charging          | Works                                                    |
| Fast Charging             | Works                                                    |
| Display Refreshing Rate   | Supports 60/90/120Hz with "Misc features / Force FPS"    |
|                           | Enable "Dynamic FPS" for dynamic switching               |
| Double Tap To Wake        | Works                                                    |
| Vibration                 | Works                                                    |

### Tweaks and Fixes

If you happen to use older GSI builds or experienced stuttering, you can try installing the module below:

[GSI Module for Infinix Note 30/Pro v2.6](https://github.com/phhusson/treble_experimentations/files/14802706/ramabp.gsioverlay.zip)

This module will fix stuttering, status bar, brightness for base Note 30, auto brightness, clock position in status bar, and enable OTG.

Use as a Magisk/KSU module.

---

**Tested By:**
- Deca1708 - Infinix Note 30 - TrebleDroid Android 14
- rama982 - Infinix Note 30 Pro - TrebleDroid Android 14
- ryenyuku - Infinix Note 30 - LineageOS 21