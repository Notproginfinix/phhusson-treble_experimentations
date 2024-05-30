### How to install?

* Flash as AP with Odin
* Reboot to recovery via recovery key combo (Vol up + power + USB connected).

### Fastboot Method
* go to Wipe > Format Data > Yes > reboot to Fastbootd.
* Open Terminal of Minimal adb or platform-tools
* run command fastboot flash system then drag gsi.img to terminal then enter

### Recovery Method
* Open TWRP Terminal, go to Wipe > Format Data > Yes and reboot recovery.
* Copy in a USB-OTG the GSI, in my case is the LineageOS 21 by Andy Yan 
* Click to install and select install image, select the GSI and flash in system partition

### ADB & Fastboot Driver

* Driver Not working ? > Go to PC > Open Device Manager > Other Driver > Right Click > Update driver > Browse my computer for drivers > Let pick from a list > Adb Interface > Samsung android Adb interface version : xxx > Next > Yes > Done (if have installed samsung driver)

### Samsung Driver Link

- [Download Driver](https://developer.samsung.com/sdp/file/de97d0ea-da03-46a4-b35d-346d37a878e0)
* Can be used with Non-samsung devices also.

### TWRP File Link

- [TWRP for S23](https://github.com/Chiharu007/treble_galaxy_s23_series/releases/download/twrp_s23_snap_series/twrp-3.7.0_12-2_afaneh92-dm1q-patched.img.tar)

- [TWRP for S23+](https://github.com/Chiharu007/treble_galaxy_s23_series/releases/download/twrp_s23_snap_series/twrp-3.7.0_12-2_afaneh92-dm2q-patched.img.tar)

- [TWRP for S23 Ultra](https://github.com/Chiharu007/treble_galaxy_s23_series/releases/download/twrp_s23_snap_series/twrp-3.7.0_12-2_afaneh92-dm3q-patched.img.tar)

## Hardware support

| Component                        |      Comment                                                                                                 |
|----------------------------------|--------------------------------------------------------------------------------------------------------------|
| Camera                           | Working                                                                                                      |
| Speaker / Mic                    | Working                                                                                                      |
| Bluetooth                        | Working                                                                                                      |
| WiFi                             | Working                                                                                                      |
| SIM / Mobile Data / Voice        | Depends on GSI                                                                                               |
| VoLTE / VoNR                     | Not Working                                                                                                  |
| Fingerprint                      | Not Working                                                                                                  |
| NFC                              | Working                                                                                                      |
| Offline Charging                 | Not tested                                                                                                   |
| 5G                               | Working maybe some gsi                                                                                      |
| 120Hz Refresh Rate               | Working                                                                                                      |
| USB-C headphones and sound cards | Working with mitigations (Settings -> Phh Treble Settings -> Samsung features -> Use alternate audio policy) |
