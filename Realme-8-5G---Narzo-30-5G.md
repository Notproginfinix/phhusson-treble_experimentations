# Realme 8 5G / Narzo 30 5G (RMX3241 / RMX3242)
## Steps to install
* Unlock bootloader (https://forum.xda-developers.com/t/a-guide-to-unlock-the-bootloader.4306487)
* Download any Phh based GSI that can be found [here](https://github.com/phhusson/treble_experimentations/wiki/Generic-System-Image-%28GSI%29-list)
* Flash GSI in fastbootd mode
  ```sh
  fastboot flash system *.img
  fastboot -w
  fastboot reboot recovery
  ```
* Flash disabled vbmeta via fastboot (only for RealmeUI 2.0) :
    ```sh
    fastboot flash --disable-verity --disable-verification vbmeta vbmeta.img 
    ```

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Back Camera               | Working                                                   |
| Front facing Camera       | Working                                                   |
| Speaker / Mic             | Working                                                   |
| Bluetooth                 | Only BT media doesn't work                                     |
| WiFi                      | Working                                                   |
| SIM / Mobile Data / Voice | Working                              |
| VoLTE                     | Working after MTK IMS setup in PHH settings                                              |
| Side Fingerprint sensor   | Partially Working                                             |
| Offline Charging          | Working                                                   |
| Tethering                 | Working                                                   |
| Hotspot                   | Works after installing this [Hotspot fix magisk module](https://t.me/Realme85G_Narzo305G_Official/13103)                                     |
| Auto-Brightness           | Working                                              |
| Headset                   | Partially Working                                              |
---
Notes:
 * Use alternative brightness scaling
 * Headset not detected until you enable "Use alternative way to detect headsets" option in PHH settings
 * Do not flash vbmeta disable on RealmeUI 3.0 and above or else the mobile network will not work.
 * Due to compatibility issue, fingerprint and face unlock option are missing in some GSI roms (Mostly Android 13 GSIs).

Tested by members of [Telegram group for these devices](https://t.me/Realme85G_Narzo305G_Official)
Template created by @zguithues and @hackintosh5
Revised by @custosoft