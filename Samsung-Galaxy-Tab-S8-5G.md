# Samsung Galaxy Tab S8 5G (gts8)

* 2024/04/25
> * ROM used for testing: [PixelOS_treble_arm64_bN-14.0-20240229](https://sourceforge.net/projects/misterztr-gsi/files/PixelOS/Android%2014/PixelOS_treble_arm64_bN-14.0-20240229.img.xz/download)
> * Auto brightness works (overlay under pull request approval)
> * Speaker Left/Right stuck on portrait mode (in landscape, bottom speaker plays left, top speaker plays right)

## Steps to install

* Unlock Bootloader (Enable OEM Unlocking, power-off, hold Vol+&- while plugging in to PC)
* Patch and Flash recovery with fastbootd (you can patch recovery with [modified script of Johx22's Patch-Recovery](https://xdaforums.com/t/patch-modify-stock-recovery-with-fastbootd-only-dynamic-samsung-devices-twrp-alternative.4643956/))
* Boot into recovery and enable fastbootd
* Flash arm64 GSI with fastboot (fastboot flash system image.img)
* Go back into recovery and Wipe Data and Cache
* Reboot!

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Front & Wide working, Ultrawide not tested                                                    |
| Speaker / Mic             | Working with some issue (see above)                                                    |
| Bluetooth                 | Bluetooth audio works. Bluetooth file transfer is untested.                                                    |
| WiFi                      | Working                                                    |
| SIM / Mobile Data / Voice | Untested                                                    |
| VoLTE                     | Untested                                                    |
| Fingerprint               | Working                                                    |
| NFC                       | N/A                                                    |
| Offline Charging          | Working                                                    |
| Galaxy Book Cover (keyboard Cover)             | Working                                                   |
| S-Pen             | Working                                                    |
---

Tested By: medkintos - SM-X706 [gts8] (XID), X706BXXS6CXB5 20240221165220 - Date tested 24/04/2024

- Template created by @zguithues and @hackintosh5