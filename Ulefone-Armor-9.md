# Ulefone Armor 9
The device generally works fine. The thermal camera and endoscope apps can be incorporated into any GSI with https://github.com/phhusson/ulefone-armor-9-gsi.

It does use A/B images despite being an A-only device.


So far the thermal camera works in Android12 GSIs if you set SElinux to permissive once (it's only needed once for some reason) with `setenforce 0` as root. I haven't managed to get it working on Android 13 though.

All this (except thermal camera) is likely applicable to the Armor 9E.


## Hardware support

| Component                 |      Comment                                          |
|---------------------------|-------------------------------------------------------|
| Camera                    | OK. See  above for thermal camera                     |
| Speaker / Mic             | OK                                                    |
| Bluetooth                 | OK                                                    |
| WiFi                      | OK                                                    |
| SIM / Mobile Data / Voice | OK                                                    |
| VoLTE                     | not tested                                            |
| Fingerprint               | OK                                                    |
| NFC                       | OK                                                    |
| Offline Charging          | OK                                                    |

## Direct link to OEM Firmware
[Ulefone Armor 9](https://drive.google.com/drive/folders/1PRFZ1Jytp_X9URya4pT6WLhkouFq_FoR)

---
Tested By: @ssorgatem - Date tested: 2022-07-11 - Template created by @zguithues and @hackintosh5
