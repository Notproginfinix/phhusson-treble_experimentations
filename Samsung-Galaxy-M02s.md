# Samsung Galaxy M02s (SM-M025F/DS)

## Steps to install

* Fastboot installation via custom fastbootd recovery (has not been tested)
    ```
    $ fastboot flash system <system.img>
    ```

* Using TWRP by OTG mouse (as touch doesn't work) (recommended)

  -> Wiping data by entering yes and then performing a Advanced wipe of system, dalvik cache, cache, and data (DO NOT SELECT ANYTHING ELSE)

  -> Selecting the GSI image to be flashed as system image. 

  -> Reboot to system (or flash gapps by rebooting to recovery again)

### Tested GSIs

- Crdroid A13 (whatsapp audio calls work for voice, but for normal voice calls might need some treble settings to be changed)
- Crdroid A14 (calls work and data also works, default camera and keyboard should be replaced other ones, tested: [simple keyboard](https://f-droid.org/en/packages/rkr.simplekeyboard.inputmethod/) and [open camera](https://f-droid.org/en/packages/net.sourceforge.opencamera/))
- Other ones are also mentioned in [this](https://xdaforums.com/t/guide-m025f-flashing-a-gsi-with-and-without-twrp.4643733/) xda post

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Works(Have to try other cam apps for better quality)      |
| Speaker / Mic             | Works                                                     |
| Bluetooth                 | Works                                                     |
| WiFi                      | Works                                                     |
| SIM / Mobile Data / Voice | Works with/without modifications in treble settings       |
| VoLTE                     | Not Working                                               |
| VoWiFi                    | Not Working.                                              |
| Fingerprint               | Has no scanner                                            |
| Offline Charging          | Maybe                                                     |
| Wi-Fi Hotspot             | Maybe                                                     |                                                 
---

## Workarounds:

### Needs further testing.

Tested By: ragebreaker - SM-M025F(INS) - Lineage-OS(Oct-23) Android-12 

Updated Date: 30 November 2023

