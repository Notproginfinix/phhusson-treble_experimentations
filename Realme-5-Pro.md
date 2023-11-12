# RMX1971

Summary of what works and doesn't.

## Steps to install

* Download any Phh based GSI
* Flash *.img file using any `custom recovery` or `fastboot`:

    ```
    $ fastboot flash system *.img && fastboot -w && fastboot reboot

    ```
## Notes
* In order to use android 14 you must flash stock rom (f.06)first.
* For Indian Jio SIM Card users, signal may not show. To fix this, go to Setting -> Network & internet -> SIMs -> Preferred network type and choose LTE (recommended) instead of 3G. Now Jio will work.
* Magisk doesn't work on android 14. (tested version 26.4)

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | working                                                   |
| Speaker / Mic             | Working                                                   |
| Bluetooth                 | Working (with audio)                                                   |
| WiFi                      | Working                                                   |
| SIM / Mobile Data / Voice | Working                                                   |
| Dual SIM                  | Working                                                   |    
| VoLTE                     | Working                                                   |
| Fingerprint               | Working                                                   |
| Hotspot / Usb tethering   | Working                                                   |
| MTP                       | Working                                                   |
---

Tested By: [abkdmn](https://t.me/abkdmn) RMX1971,  Version: [PHH Android 14 r14](https://github.com/TrebleDroid/treble_experimentations/releases/tag/ci-20231107)                                                      