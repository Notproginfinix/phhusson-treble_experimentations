# Device

Works. Display brightness can be dimmed beyond visibility, control it with caution. To use wired headphones, turn "Force headset switch" and "Use alternate way to detect headphones" on, then reboot.
## Steps to install

* Register Infinix account, log in from phone
* Wait for 2 weeks
* Turn "bootloader unlock" and "USB debugging" switches on
* Unlogin Google and Infinix accounts, disable screen locking
* adb reboot bootloader
* fastboot flashing unlock
* Press "volume up" button
* fastboot reboot
* Check if bootloader actually unlocked
* adb reboot bootloader
* Flash Google's vbmeta.img
* fastboot reboot fastboot
* Remove unneeded dynamic partitions from super partition, you can list them with "fastboot getvar all" command. Keep system_* and vendor_* partitions.
* fastboot erase system_a
* Flash GSI image
* With volume up, volume down and power buttons enter recovery
* Perform factory reset
* Reboot

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Works                                                    |
| Speaker / Mic             | Works                                                    |
| Bluetooth                 | Works                                                    |
| WiFi                      | Works, both 2.4 GHz and 5 GHz                                                    |
| SIM / Mobile Data / Voice | Works                                                    |
| VoLTE                     | I don't know                                                    |
| Fingerprint               | Works                                                    |
| NFC                       | Not present                                                    |
| Offline Charging          | Works                                                    |
|GPS|Hasn't checked yet|
|OTG|Does not work?|
---