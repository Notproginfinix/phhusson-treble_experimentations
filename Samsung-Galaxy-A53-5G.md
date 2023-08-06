# Samsung Galaxy A53 5G

Summary of what works and doesn't

## Steps to install

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
| SIM / Mobile Data / Voice        | Working (if not, try to reflash the GSI)                                                                 |
| VoLTE                            | Not Working                                                                                                  |
| Fingerprint                      | Working                                                                                                      |
| NFC                              | Working                                                                                                      |
| Offline Charging                 | Working                                                                                                      |
| 5G                               | Not Working                                                                                                  |
| 120Hz Refresh Rate               | Working                                                                                                      |
| USB-C headphones and sound cards | Working with mitigations (Settings -> Phh Treble Settings -> Samsung features -> Use alternate audio policy) |

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
