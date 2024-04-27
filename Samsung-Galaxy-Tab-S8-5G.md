# Samsung Galaxy Tab S8 5G (gts8)

## Wiki Changelog/Status
* 2024/04/25
> * ROM used for testing: [PixelOS_treble_arm64_bN-14.0-20240229](https://sourceforge.net/projects/misterztr-gsi/files/PixelOS/Android%2014/PixelOS_treble_arm64_bN-14.0-20240229.img.xz/download)
> * Auto brightness works (overlay under pull request approval)
> * Speaker Left/Right stuck on portrait mode (in landscape, bottom speaker plays left, top speaker plays right)

* 2024/04/28
> * Overlay have been merged!
> * Add partial fix for the speaker orientation (credit phhusson himself!)

## Steps to install
### Flashing
* Unlock Bootloader (Enable OEM Unlocking, power-off, hold Vol+&- while plugging in to PC)
* Patch and Flash recovery with fastbootd (you can patch recovery with [modified script of Johx22's Patch-Recovery](https://xdaforums.com/t/patch-modify-stock-recovery-with-fastbootd-only-dynamic-samsung-devices-twrp-alternative.4643956/))
* Boot into recovery and enable fastbootd
* Flash arm64 GSI with fastboot (fastboot flash system image.img)
* Go back into recovery and Wipe Data and Cache
* Reboot!

### Installing overlay (for auto brightness and power profile on builds before April 2024)
* Install Magisk (and another required module for Play Integrity/Widevine)
* Flash attached file [here](https://xdaforums.com/t/installing-lineageos-gsi-on-tabs8-8-8ultra-fastbootd-edition.4660519/post-89479747) on magisk
* Reboot!

### Fix stereo audio sound orientation (credit phhusson)
As the left & right channel stuck in Portrait position, in landscape mode the left & right speaker play the left & right channel (creating somewhat mono sound)

On Samsung firmware, the sound orientation will change automatically, which isn't on GSIs. To partial fix this:
* Get into ADB Shell (or Termux but not tested) and type `am start-service me.phh.treble.app/.REPL` then wait for 10 seconds
* After that, type/paste this:

> `echo '"g_hw_display_rotation=1 :android.media.AudioSystem .setParameters' | timeout 1 busybox_phh nc localhost 8800`
> * Set the g_hw_display_rotation value with your daily tablet orientation use (optional):
>> * `0` = Portrait (default)
>> * `1` = Landscape (prompt above)
>> * `2` = Reverse portrait
>> * `3` = Reverse landscape
* Profit!

You must do this every time you do reboot. Proper fix will be implemented soon on TrebleApp by the respected developer (as i can't code)


***


## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Auto Brightness           | Will work for builds after 26/04/2024                                                    |
| Camera                    | Front & Wide working, Ultrawide not tested                                                    |
| Speaker / Mic             | Working with some issue (see above)                                                    |
| Bluetooth                 | Bluetooth audio works. Bluetooth file transfer is untested.                                                    |
| WiFi                      | Working                                                    |
| SIM / Mobile Data / Voice          | Untested                                                    |
| VoLTE                              | Untested                                                    |
| Fingerprint                        | Working                                                    |
| NFC                                | N/A                                                    |
| Offline Charging                   | Working                                                    |
| Galaxy Book Cover (keyboard Cover) | Working                                                   |
| S-Pen             | Working                                                    |
---

Tested By: medkintos - SM-X706 [gts8] (XID), X706BXXS6CXB5 20240221165220 - Date tested 24/04/2024

- Template created by @zguithues and @hackintosh5