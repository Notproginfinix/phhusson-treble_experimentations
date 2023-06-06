### How to install?
* Flash [TWRP ](https://forum.xda-developers.com/t/recovery-unofficial-twrp-for-galaxy-s23.4558749/) as AP and [VBMETA Disabler](https://forum.xda-developers.com/attachments/vbmeta_disabled_r-tar.5236537/?hash=f7249adaefe16f3aeac3256a63063f0a) as USERDATA with Odin
* Reboot to recovery via recovery key combo (Vol up + power + USB connected).
* Open TWRP Terminal, go to Wipe > Format Data > Yes and reboot recovery.
* Copy in a USB-OTG the GSI, in my case is the LineageOS 20 by Andy Yan 
* Click to install and select install image, select the GSI and flash in system partition

## Hardware support

| Component                        |      Comment                                                                                                 |
|----------------------------------|--------------------------------------------------------------------------------------------------------------|
| Camera                           | Working                                                                                                      |
| Speaker / Mic                    | Working                                                                                                      |
| Bluetooth                        | Working                                                                                                      |
| WiFi                             | Working                                                                                                      |
| SIM / Mobile Data / Voice        | Depends on GSI                                                                                               |
| VoLTE                            | Not Working                                                                                                  |
| Fingerprint                      | Not Working                                                                                                      |
| NFC                              | Working                                                                                                      |
| Offline Charging                 | Not tested                                                                                                 |
| 5G                               | Not Working                                                                                                  |
| 120Hz Refresh Rate               | Working                                                                                                      |
| USB-C headphones and sound cards | Working with mitigations (Settings -> Phh Treble Settings -> Samsung features -> Use alternate audio policy) |