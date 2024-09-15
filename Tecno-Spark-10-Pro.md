# Tecno Spark 6
###### also known as TECNO KI7 / K17

Everything works except for fast charging. Limited to 2000mAh (or atleast, I couldn't get it to work)

Tested with crDroid ([crDroid-10.5 v2024.05.15](https://github.com/naz664/crDroid_gsi/releases/tag/v2024.05.15)) (recommended),
Project Elixir (laggy) and RisingOs (buggy, broken microphone)

## Steps to install

* Enable OEM unlock in Developer options then unlock the bootloader (Need active TECNO account > 15d old)
* Reboot into fastboot mode:
    ```
    $ adb reboot fastboot
    ```
* Re-flash the stock `vbmeta.img` / [google one](https://dl.google.com/developers/android/qt/images/gsi/vbmeta.img) with verification disabled:
    ```
    $ fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
    ```
* Empty out logical partitions used by the stock ROM to free some space [placebo.img](https://t.me/UniversalGSI/97834):
    ```
    $ fastboot flash product placebo.img
    $ fastboot flash system_ext placebo.img
    ```
* Flash the system image with the GSI build you want to put on:
    ```
    $ fastboot flash system gsi.img
    ```


## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Working                                                   |
| Speaker / Mic             | Working                                                   |
| Bluetooth                 | Working                                                   |
| WiFi                      | Working                                                   |
| SIM / Mobile Data / Voice | Working                                                   |
| VoLTE                     | Working                                                   |
| Fingerprint               | Working                                                   |
| NFC                       | Working maybe?? Not tested                                |
| Fast Charging             | Not working                                               |
| Offline Charging          | Working                                                   |
---


Tested By: [khaled-0](https://github.com/khaled-0) - TECNO Spark 10 Pro (KI7)