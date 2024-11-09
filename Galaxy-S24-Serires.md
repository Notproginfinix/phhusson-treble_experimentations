### How to install?
* Flash as AP with Odin
* Reboot to recovery via recovery key combo (Vol up + power + USB connected).

### Fastboot Method
* go to Wipe > Format Data > Yes > flash boot_repack.zip > reboot to Fastbootd.
* Open Terminal of Minimal adb or platform-tools
* run command fastboot flash system then drag gsi.img to terminal then enter

### Recovery Method
* Open TWRP Terminal, go to Wipe > Format Data > Yes > flash boot_repack.zip > and reboot recovery.
* Then Copy in a USB-OTG the GSI, in my case is the LineageOS 21 by Andy Yan 
* Click to install and select install image, select the GSI and flash in system partition

### Boot_Repack Link
- [boot_repack.zip](https://xdaforums.com/attachments/boot_repack-zip.5848071/?hash=2d10d9951d7d44c38d90d7b7d9d7fda9) (To fix stock recovery restoration)

### ADB & Fastboot Driver
* Driver Not working ? > Go to PC > Open Device Manager > Other Driver > Right Click > Update driver > Browse my computer for drivers > Let pick from a list > Adb Interface > Samsung android Adb interface version : xxx > Next > Yes > Done (if have installed samsung driver)

### Samsung Driver Link

- [Download Driver](https://developer.samsung.com/sdp/file/de97d0ea-da03-46a4-b35d-346d37a878e0)
* Can be used with Non-samsung devices also.

## Force Refresh rate 120HZ
* Adb Method
```
adb shell settings put system min_refresh_rate 120
adb shell settings put system peak_refresh_rate 120
```

* Settings Method
```
Settings -> Phh Treble Settings -> Misc -> Force FPS
```

## Hardware support

| Component                        |      Comment                                                                                                 |
|----------------------------------|--------------------------------------------------------------------------------------------------------------|
| Camera                           | Working                                                                                                      |
| Speaker / Mic                    | Working                                                                                                      |
| Bluetooth                        | Working                                                                                                      |
| WiFi                             | Working                                                                                                      |
| SIM / Mobile Data / Voice        | Depends on GSI                                                                                               |
| VoLTE / VoNR                     | Not Working                                                                                                  |
| Fingerprint                      | Not Tested                                                                                                  |
| NFC                              | Working                                                                                                      |
| Offline Charging                 | Not tested                                                                                                   |
| 5G                               | Working                                                                                     |
| 120Hz Refresh Rate               | Working                                                                                                      |
| USB-C headphones and sound cards | Working with mitigations (Settings -> Phh Treble Settings -> Samsung features -> Use alternate audio policy) |
