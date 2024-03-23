# Tecno Camon 20 Pro
###### also known as TECNO CK7n

Works fine as expected, however, there are some flaws when using custom ROMs:
- Project Elixir does not boot successfully when B slot is only flashed
- SIM networks are unable to get coverage on some GSI builds (LineageOS)

Tested with crDroid, EvoX, LineageOS, and Project Elixir (Android 13 & 14)

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
* Ensure the device is using the A slot, if not, do:
    ```
    $ fastboot --set-active=a
    ```
* Delete logical partitions used by the stock ROM to free some space:
    ```
    $ fastboot delete-logical-partition product_a
    $ fastboot delete-logical-partition system_ext_a
    ```
* Flash the system image with the GSI build you want to put on:
    ```
    $ fastboot flash system gsi.img
    ```

    As an alternative you can flash via TWRP as "System Image" and format data.

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Working                                                   |
| Speaker / Mic             | Working                                                   |
| Bluetooth                 | Working                                                   |
| WiFi                      | Working                                                   |
| SIM / Mobile Data / Voice | Partially Working                                         |
| VoLTE                     | Working                                                   |
| Fingerprint               | Not Working                                               |
| NFC                       | Working                                                   |
| Fast Charging             | Working                                                   |
| Offline Charging          | Working                                                   |
---

## Tweaks
### Enable VoLTE
Go to Settings -> Phh Treble Settings -> Misc -> Install IMS APK for MediaTek S Vendor
then reboot

Tested By: [spir0th](https://github.com/spir0th) - TECNO Camon 20 Pro (CK7n-GL), CK7n-H894ABC-T-GL-240218V2320 - Last edited on 03/23/24 - Template created by @zguithues and @hackintosh5