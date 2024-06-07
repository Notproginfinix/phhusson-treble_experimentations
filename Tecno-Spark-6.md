# Tecno Spark 6
###### also known as TECNO KE7

Works fine as expected, however, there are some flaws when using custom ROMs:

- After installing Android 14 you may not be able to use the pasts versions of Android and even STOCK so proceed with caution. ⚠️


Tested with Derpfest (QPR1 works fine feb patch) (recommended), EvoX (buggy), LineageOS, and RisingOs (buggy) (Android 14)

## Steps to install

* Enable OEM unlock in Developer options then unlock the bootloader
* Reboot into fastboot mode:
    ```
    $ adb reboot fastboot
    ```
* Re-flash the stock `vbmeta.img` with verification disabled:
    ```
    $ fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
    ```
* Delete logical partitions used by the stock ROM to free some space:
    ```
    $ fastboot delete-logical-partition product
    $ fastboot delete-logical-partition system
    ```
* Flash the system image with the GSI build you want to put on:
    ```
    $ fastboot flash system gsi.img
    ```

    As an alternative you can flash via fastbootd as "System Image" and format data.

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Working                                                   |
| Speaker / Mic             | Working                                                   |
| Bluetooth                 | Working                                                   |
| WiFi                      | Working                                                   |
| SIM / Mobile Data / Voice | Working                                       |
| VoLTE                     | Working                                                   |
| Fingerprint               | Working                                              |
| NFC                       | Not Available                                                 |
| Fast Charging             | Not Available                                                |
| Offline Charging          | Working                                                   |
---

## Tweaks
### Enable VoLTE
Go to Settings -> Phh Treble Settings -> Misc -> Install IMS APK for MediaTek Q Vendor
then reboot

Tested By: [johncarl2234](https://github.com/johncarl2234) - TECNO Spark 6 (KE7)