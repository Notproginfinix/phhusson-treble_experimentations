# Infinix Note 8 (X692)

Overall excellent, things are working as expected.

Tested with Phh's GSI, LineageOS, CAOS, and PixelExperience (Android 10, 11, 12, & 13)

## Steps to install

* Grab an ARM64 A/B GSI ROM image [here](https://github.com/phhusson/treble_experimentations/wiki/Generic-System-Image-%28GSI%29-list) or from other source,
* Unlock the bootloader and go into bootloader mode,
* Reflash the original vbmeta image but with verification disabled using the `fastboot` utility;
    ```
    $ fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
    ```
* Reboot to fastboot mode;
    ```
    $ fastboot reboot fastboot
    ```
* Flash the system image with the `fastboot` utility:
    ```
    $ fastboot flash system system-image.img
    ```

* Tips: If you ran out of system partition space, you can remove the `product` partition by doing the following:
    ```
    $ fastboot delete-logical-partition product
    ```

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | OK                                                        |
| Speaker / Mic             | OK                                                        |
| Bluetooth                 | OK                                                        |
| WiFi                      | OK                                                        |
| Hotspot / Tethering       | OK                                                        |
| SIM / Mobile Data / Voice | OK                                                        |
| VoLTE                     | OK (Android ≥11)                                          |
| Fingerprint               | OK                                                        |
| NFC                       | Unsupported                                               |
| Offline Charging          | OK                                                        |
---

## Additional Note

* This device uses ARM64 CPU architecture and A/B image (because of the system-as-root partition scheme), but does not support seamless update.

Tested By: [リェンーゆく (ryenyuku)](https://github.com/ryenyuku) @ Infinix Note 8 (x692), X692-H694KLMX-Q-GL-220311V412 - Last edited on 11/09/2023 - Template created by @zguithues and @hackintosh5