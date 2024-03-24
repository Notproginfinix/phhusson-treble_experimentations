# Cubot King Kong Mini 2
The device generally works fine.
Thanks to @highbiker for his tip on rebooting to fastboot, taken from [this XDA forum post](https://forum.xda-developers.com/t/installing-custom-rom-on-cubot-kingkong-mini.4050815/page-9#post-84445303).

I successfully installed and tested the following ROMs, all of them work fine:
* [system-td-arm32_binder64-ab-vanilla.img](https://github.com/TrebleDroid/treble_experimentations/releases) by @phhusson (AOSP 14)
* [lineage-18.1-20210512-UNOFFICIAL-treble_a64_bvS.img](https://sourceforge.net/projects/andyyan-gsi/files/lineage-18.x/) by @AndyYan
* [Havoc-OS-v3.8-20200821-Official-a64-ab.img](https://download.havoc-os.com/?dir=a64-ab) (I also tried v4.4 but it didn't boot)

## Steps to install

* Enable USB debugging and OEM unlocking in developer options and reboot to bootloader
    ```
    adb reboot bootloader
    ```
* Unlock device
    ```
    fastboot flashing unlock
    ```
* Disable Android Verified Boot 2.0

    This requires `vbmeta.img` from the stock ROM (only needed once).
    ```
    fastboot flash --disable-verity --disable-verification vbmeta vbmeta.img
    ```
* Reboot to fastboot
    ```
    fastboot reboot fastboot
    ```
* flash image
    ```
    fastboot flash system system-td-arm32_binder64-ab-vanilla.img
    ```

## Hardware support

| Component                 |      Comment                                          |
|---------------------------|-------------------------------------------------------|
| Camera                    | OK                                                    |
| Speaker / Mic             | OK                                                    |
| Bluetooth                 | OK                                                    |
| WiFi                      | OK                                                    |
| SIM / Mobile Data / Voice | OK                                                    |
| VoLTE                     | OK                                                    |
| VoWifi                    | works with Stock-ROM, but not with LOS18.1            |
| Fingerprint               | N/A                                                   |
| NFC                       | N/A                                                   |
| Offline Charging          | OK                                                    |

## Direct link to OEM Firmware
[CUBOT_KINGKONG MINI2_A061C_V11_20220817](https://mega.nz/file/hQM23AjY#MCrXut2Ho0R6Rk-p50Yf28fE_HKvvuLaHPpX8K1ynds)

---
Template created by @zguithues and @hackintosh5
