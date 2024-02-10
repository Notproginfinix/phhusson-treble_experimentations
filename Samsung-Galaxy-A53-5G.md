# Samsung Galaxy A53 5G

Summary of what works and doesn't

## Steps to install

### Newer firmwares

As afaneh stopped maintaining the permissive kernel and TWRP and nobody replaced him, his permissive kernel is likely broken on newer OneUI versions. At least I couldn't get it to install and successfully boot on OneUI 6 (Android 14). This makes installation a bit harder.

Make sure your bootloader is already unlocked. Below procedure **WILL** delete all your data, so please make a backup of anything important. This procedure presumes you already have Odin and Android Studio with fastboot installed. If not, please install Odin from [here](https://xdaforums.com/t/patched-odin-3-13-1.3762572/) (only for Windows) and Android Studio from [here](https://developer.android.com/studio). You can install fastboot from within Android Studio. 

1. Download files from [latest release](https://github.com/mytja/Patch-Recovery)

If your Samsung device already has fastbootd, boot into fastboot and skip straight to step 8! Your Samsung device should be plugged into your computer from now on, with USB debugging enabled.

2. Boot into Download Mode by holding VOL UP and VOL DOWN simultaneously when the device is off. Alternatively, you can run `adb reboot download`.

3. TURN OFF AUTO RESTART IN ODIN (options tab), AS RESTARTING TO STOCK ROM WILL WIPE CUSTOM RECOVERY!

4. Select patched recovery (`.tar.md5` file) as AP file and `vbmeta` (`.tar` file) as USERDATA. This is enables fastboot, as modern Samsung devices don't have this feature enabled.

5. Once flash is complete, hold VOL DOWN and SIDE KEY (power button) to exit Download Mode, then IMMEDIATELY change to VOL UP and SIDE KEY (power button) when screen goes black. If you screw this up and you don't time it correctly, you'll end up booting in best case in OneUI or in worst case a bootloop. You'll need to repeat the before mentioned procedure (go back to step 2).

6. Press the VOL UP and VOL DOWN buttons to select the fastboot option once in Android recovery.

7. Press SIDE KEY to boot into fastbootd.

8. Run `fastboot devices` in Windows Terminal or Command Prompt to ensure the device is recognized.

9. If your GSI came in a compressed file (.xz, .zip, etc.) extract it with your program of choice. You should be left with a .img file. Rename this file to system.img. All of this should be done in your downloads folder.

10. Navigate your command prompt using `cd` to your Downloads folder. In my case, it was `cd C:\Users\User\Downloads\`. Your username might be different.

11. Run `fastboot erase system`.

12. Run `fastboot flash system system.img`. This might take a few minutes to complete. If you get an error about system partition size, scroll to the bottom of [this article](https://source.android.com/docs/setup/create/gsi) and run the command to free up space.

13. Once complete, run `fastboot -w`. If this returns an error, do not retry and proceed to the next step. If it ran successfully, do a `fastboot reboot` and enjoy your newly flashed GSI.

14. Select an option "Enter recovery" or something similar and select it by clicking the SIDE KEY (power button). You should be transferred back to the recovery. In case you accidentally rebooted the system, you will have to return to step 11. In a worst case scenario, you may have to go to the PANIK GUIDE to completely reset, then go from step 1. Alternatively, you may also do a `fastboot reboot recovery`.

15. Use VOL UP and VOL DOWN to select 'Wipe Data/Factory Reset' and use SIDE KEY to confirm.

16. After wiping data, use VOL UP and VOL DOWN to reboot (should be the first option in Android recovery).

17. You should get rebooted to your newly flashed GSI. Enjoy.

### Legacy

* Flash [TWRP](https://www.androidfilehost.com/?w=files&flid=335166) as AP and [VBMETA Disabler](https://forum.xda-developers.com/attachments/vbmeta-tar.5956063/) as USERDATA with Odin.

* Reboot to recovery via recovery key combo (Vol up + power + USB connected).

* Open TWRP Terminal, execute "multidisabler" command, then go to Wipe > Format Data > Yes and reboot recovery.

* [ADB](https://developer.android.com/studio/releases/platform-tools) Push [this kernel zip](https://www.androidfilehost.com/?w=files&flid=335167) to /sdcard

* Flash the pushed ZIP (GSI won't boot without it.)

* Flash any GSI image as system image in TWRP, then reboot system and enjoy.

## Hardware support

| Component                        |      Comment                                                                                                 |
|----------------------------------|--------------------------------------------------------------------------------------------------------------|
| Camera                           | Working                                                                                                      |
| Speaker / Mic                    | Working                                                                                                      |
| Bluetooth                        | Working                                                                                                      |
| WiFi                             | Working                                                                                                      |
| SMS                              | Not Working (as of SW rev. 8 firmware)                                                                   |
| SIM / Mobile Data / Voice        | Working (if not, try to reflash the GSI)                                                                 |
| VoLTE                            | Not Working                                                                                                  |
| Fingerprint                      | Working                                                                                                      |
| NFC                              | Working                                                                                                      |
| Offline Charging                 | Working                                                                                                      |
| 5G                               | Not Working                                                                                                  |
| 120Hz Refresh Rate               | Working                                                                                                      |
| USB-C headphones and sound cards | Working with mitigations (Settings -> Phh Treble Settings -> Samsung features -> Use alternate audio policy) |

### Mitigations for non-working SMS
If you've upgraded to one of Samsung's newer firmwares, most likely 7 and 8, you will encounter an issue where you won't be able to send any SMS messages (Error 0 is shown in Google Messages). You won't either be able to receive them. Calls and mobile data should operate normally.

In case you encounter such an issue, you may want to downgrade to one Android 13 GSI. Per my testing, only receiving seems to be broken, SMS sending works on Android 13 GSIs.

The developers of TrebleDroid are currently working on this issue.

## GSI support
Android 13 GSIs are supported (only VNDK). Bootloops while running on VNDKlite vendor. Android 12 GSIs are supported (both VNDK and VNDKlite).

### GSIs tested

- [Lineage TD 20.0 - Android 13](https://sourceforge.net/projects/andyyan-gsi/files/lineage-20-td/) - tested with `bvN` as well as `bgN` with VNDK vendor, `vndklite` didn't feel like booting. Seems that Universal SafetyNet Fix interferes with Google apps (including Messages, Drive and GMail) and makes them crash upon opening. It might just be my phone, but proceed with caution. Tested on 28/07/2023 by mytja.
- [PixelOS 13.0](https://sourceforge.net/projects/misterztr-gsi/files/PixelOS/Android%2013/) - **didn't boot**, stuck on Google logo, connecting and disconnecting from my computer every 10-60 seconds. Tested on 29/07/2023 by mytja.
- [Pixel Experience 13.0](https://github.com/ponces/treble_build_pe/releases/) - tested with `VNDK` vendor (not `slim` or `vndklite`), first time it didn't want to connect to WiFi during setup, reboot didn't help, had to reinstall the image to make it work. After having it installed for more than a week, everything listed in above table seems to be correct (only 5G and VoLTE not working due to Samsung's proprietary design).
- [Lineage 19.1 - Android 12](https://sourceforge.net/projects/andyyan-gsi/files/lineage-19.x/) - tested with `bvN` and both vendors (`VNDKlite` and `VNDK`). Universal SafetyNet Fix interferes with some Google apps, but less than on Lineage 20. Tested on 18/05/2023 by mytja.

---

Tested By: ItsLynix - SM-A536B(EUX), A536BXXU4BVL2 - 01/02/2023 - Template created by @zguithues and @hackintosh5

Tested By: mytja - SM-A536B(EUX), A536BZKNEEE - 18/05/2023 - LineageOS GSI 19.1

Tested By: mytja - SM-A536B(EUX), A536BZKNEEE - 29/07/2023 - Pixel Experience Plus 13.0