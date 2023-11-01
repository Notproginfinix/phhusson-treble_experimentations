# Device

AOSP boots, WiFi, cellular data works, sound works

## Steps to install

PWR + VOL+ --> Recovery

PWR + VOL- --> Bootloader

* Unlock bootloader in fastboot mode (`vbmeta.img` and `vbmeta_system.img` are taken from the STOCK ROM, or it will bootloop!):
    ```
    $ fastboot flashing unlock
    $ fastboot --disable-verification --disable-verity flash vbmeta vbmeta.img
    $ fastboot --disable-verification --disable-verity flash vbmeta_system vbmeta_system.img
    ```
    **WARNING: Unlocking will VOID YOUR WARRANTY and make fingerprint UNUSABLE! You may try this to recover fingerprint: https://forum.xda-developers.com/t/guide-for-calibration-finger-print-after-loss-data-calibration.4132961/ WITH STOCK ROM, to see if it worked!**
* Enable ADB from stock ROM
* Enter `fastbootd` mode from adb:
    ```
    $ adb reboot fastboot
    ```
* Or enter `fastbootd` mode from fastboot:
    ```
    $ fastboot reboot fastboot
    ```
* Flash this image with the `fastboot` utility:
    ```
    $ fastboot flash system system-td-arm64-ab-vanilla.img 
    ```
* Reboot (or wipe device from stock recovery).

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Works                                                     |
| Speaker / Mic             | Works better with "Qualcomm features / Use alternative audio policy" |
| Headphone                 | Works |
| USB DAC                   | Works |
| Type-C DP Alt mode        | Works |
| GPS                       | Works |
| Bluetooth                 | Works |
| NFC **                | Works (Global version) |
| WiFi                      | Works |
| SIM / Mobile Data / Voice | Works |
| Tethering                 | Works |
| Proximity Sensor          | Works |
| Accelerometer / Gyroscope | Works |
| VoLTE                     | Not working (China Telecom) (Works with steps in https://github.com/phhusson/treble_experimentations/issues/1681, but not persisted across reboots)                                                    |
| RCS Message *              | Works |
| Fingerprint *              | Works |
| Auto Brightness *                | Works |
| Offline Charging          | Works                                                    |
| Quick Charging            | Works  |
| Fan Control *               | Works with "Nubia features / FAN speed" (Supported auto start/stop depending on charging state)                                                    |
| Logo LED                  | Not working |
| RGB LEDs                  | Works with "Nubia features / REDMAGIC RGB" |
| Display Refreshing Rate   | Supports 60/90/120/144/165Hz with "Misc features / Force FPS" |
| Double Tap To Wake Up (dt2w) *                 | Works with "Nubia features / Enable DT2W"  |
| Shoulder Buttons          | Not working |
| Back Panel Button               | Not working |
| Side Switch               | Not working |
| Vibration                 | Works |

\* (TrebleDroid Android >= 14)

\** The Chinese version doesn't have NFC. If you want to stop hwmanager from flooring log with (init: try to start nfc): 
- Root with magisk and install module [magic_overlayfs](https://github.com/HuskyDG/magic_overlayfs). 
- Then run open termux and run cmd: `su -mm -c magic_remount_rw` to enable r/w. 
- Open any file explorer and go to `/odm/etc/vintf/` then remove `manifest_nfc.xml`.
- Next, go to `/odm/etc/permissions/sku_nfc/` and remove all files starting with `android.hardware.nfc`.


## Tweaks

| Name | Comment |
|------|---------|
|Rounded corners|Set "Misc features / Set rounded corners diameter" to 30~40 and reboot|
|Boost CPU| For faster fingerprint scanning|

## Notes

2. You can re-lock your bootloader with stock ROM to restore your fingerprint. Back up your persist partition.
3. Nubia is using the test key(external/avb/test/data/testkey_rsa4096.pem) to sign boot, vendor_boot, dtbo and odm partitions. You can create a new `vbmeta.img` with this key from AOSP and keep Magisk with a locked bootloader, also get the working fingerprint.
4. Unbrick tool (Go to EDL mode, Open miflashtool > select `images` folder and click "flash"):
- 6/6pro: https://drive.google.com/file/d/15QjRvedmB7J7bJPqffMdKQ4qnWMtIWm-/view?usp=drivesdk
- 6s/6spro: https://drive.google.com/file/d/12udr9yKexzLCpBjB0lwhSNU6C6poKOhR/view?usp=sharing
---
Tested By: 
- notsyncing - NX669J(CN), AOSP 11.0 v302 - 2021/03/12 - Template created by @zguithues and @hackintosh5
- boydaihungst - NX669J(CN), TrebleDroid AOSP 14.0 2023/10/21