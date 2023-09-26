# Galaxy A01Core SM-A013G

## Steps to install

* Unlock Bootloader
* Flash with Odin supported fastbootD recovery (I don't have link now. it's can be found in 4pda). 
* Reboot to recovery and select enter fastboot
* Delete /product `fastboot delete-logical-partition product`
* Flash system.img `fastboot flsah system /path/to/your/file`
* Wait for finish, and select enter recovery
* Wipe data&&cache
* Reboot to system

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Yes.                                                 |
| Speaker / Mic             | Working. headset not working.                                                    |
| Bluetooth                 | No tested.                                                    |
| WiFi                      | Working.                                                   |
| SIM / Mobile Data / Voice | Working (SMS/Calls). Mobile data Not working.                                                    |
| VoLTE                     | No tested.|
| Fingerprint               | ----------                                                    |
| NFC                       | ----------                                                    |
| Offline Charging          | Working.                                                   |
| Other feature             | MTP no working. (ADB working)  to turn on from charging mode, need press down volume+power some sec.                                                |
---

Tested By: @AshiVered.
ROM tested: [lir 18 (Android 11)](https://sourceforge.net/projects/treblerom/files/LiR/2022.03.25/lir-v316-220325-a64-bvZ-lite.img.xz/download) Tried other ROMs too but they were more buggy.