# [Nokia X10] - [scarletwitch / SCW]
**Bootloader Unlock**: 
* Not fun to do. Guide: [Bootloader unlocking and rooting the Nokia X10](https://xdaforums.com/t/bootloader-unlocking-and-rooting-the-nokia-x10.4584169/)
   
**ROMs tested**:
1. Project Elixir v4.1 / `ProjectElixir-4.1-arm64-bgN-14.0-20240226-1114-OFFICIAL.img.xz` - **DOA, STUCK IN BOOTLOOP AFTER FLASHING** 
    * problem is caused by the ROM itself, however, not the device.
    * version v4.2 is also already out, so if you manage to get out of the bootloop and into the setup screen - congrats, please update this page.
    * if not, please go to Project Elixir's [Telegram channel](https://t.me/universalgsi) for support. Also, please pay attention to this [message](https://t.me/UniversalGSI/1/77948) on the channel, it might be useful for submitting bug reports.
2. MikuUI Snowland v0.7.0 / `MikuUI-SNOWLAND-0.7.0-arm64-ab-gapps-20220725-UNOFFICIAL.img.xz` - **SUCCESSFULLY BOOTED AND WORKED JUST FINE**
    * VNGamerGit (hereby referred to as "I") installed the ROM via [DSU Sideloader](https://github.com/VegaBobo/DSU-Sideloader), however, and as of now, I still do not know what's the difference between a full bare-metal install and an installation from the tool, so please let me know if it's different.
    * Also, the ROM is already discontinued. I'll try newer versions one day. No promises though!
3. LeOS U / `LeOS-U-VNDK-arm64-bvN-0224.img.xz` - **SUCCESSFULLY BOOTED AND WORKED JUST FINE**
    * I installed the ROM just right before I sent my phone for repairing, not to mention that the ROM lacked even a camera app (if I remember correctly) so I didn't get to test the ROM much.
    * So, please take my report on its hardware support with a grain of salt, I guess.
4. Evolution X / `evolutionX-8.3_arm64_bgN-RO.img.xz` (YukiMetaa's [build](https://github.com/YukiMetaa/treble_evolution/releases/tag/8.3-udc_21032024)) - **SUCCESSFULLY BOOTED AND WORKED JUST FINE, CURRENT DAILY DRIVER FOR VNGAMERGIT**

# Hardware support (Project Elixir v4.1):
| Component                 | Working? (✅/❌/❓)   |              Comment             |
|---------------------------|------------------------|----------------------------------|
| Camera                    |            ❌            |      NULL (DID NOT BOOT)         |
| Speaker / Mic             |            ❌            |      NULL (DID NOT BOOT)         |
| Bluetooth                 |            ❌            |      NULL (DID NOT BOOT)         |
| WiFi                      |            ❌            |      NULL (DID NOT BOOT)         |
| SIM / Mobile Data / Voice |            ❌            |      NULL (DID NOT BOOT)         |
| VoLTE                     |            ❌            |      NULL (DID NOT BOOT)         |
| Fingerprint               |            ❌            |      NULL (DID NOT BOOT)         |
| NFC                       |            ❌            |      NULL (DID NOT BOOT)         |
| Offline Charging          |            ❌            |      NULL (DID NOT BOOT)         |
| Other features            |            ❌            |      NULL (DID NOT BOOT)         |

# Hardware support (MikuUI Snowland)
| Component                 | Working? (✅/❌/❓)   |              Comment             |
|---------------------------|------------------------|----------------------------------|
| Camera                    |           ❓           | Built-in camera app gives out pictures that have "okay" quality, but they all turned out green. |
| Speaker / Mic             |           ✅             |                                  |
| Bluetooth                 |           ✅             |                                  |
| WiFi                      |           ✅             |                                  |
| SIM / Mobile Data / Voice |           ❓             | Haven't thoroughly tested the function out. |
| VoLTE                     |           ❓             | Haven't thoroughly tested the function out.  |
| Fingerprint               |           ✅            |                                  |
| NFC                       |           ❓             | Don't know where to even test NFC, but it could be turned on. |
| Offline Charging          |           ❓1            |  |
| Other features            |           ❓            | wut                                |
> 1: Since I tested the ROM on DSU Sideloader, if I turn the phone off then I'd reboot back to the firmware installed on my regular slot, so no idea if this works.

> Also, it's been a long time since I ran the ROM (all the way back to a few days after the upload date of the bootloader unlock guide), my memory is hazy.

# Hardware support (LeOS U):
| Component                 | Working? (✅/❌/❓)   |              Comment             |
|---------------------------|------------------------|----------------------------------|
| Camera                    |            ❓            | No pre-installed camera apps, not to mention I removed the ROM right away for Evolution X, but I assume that any Google Camera ports will work.  |
| Speaker / Mic             |            ✅            |          |
| Bluetooth                 |            ❓            | Reinstalled right away after getting the phone back from repair, so no idea.         |
| WiFi                      |            ❌            | Tried connecting to home network (both Wi-Fi 5GHz and 2.4GHz), could connect but always end with not having internet access.  |
| SIM / Mobile Data / Voice |            ❓            |Same as Bluetooth.         |
| VoLTE                     |            ❓            |Same as Bluetooth.         |
| Fingerprint               |            ❓            |Same as Bluetooth.         |
| NFC                       |            ❌            |No idea where to test NFC, and it couldn't even be turned on too.         |
| Offline Charging          |            ❌            |Plugging in the phone while it's turned off always ends in it booting up.         |
| Other features            |            ❓            |wut         |


# Hardware support (Evolution X 8.3):
| Component                 | Working? (✅/❌/❓)   |              Comment             |
|---------------------------|------------------------|----------------------------------|
| Camera                    |            ✅1            |    Just don't use the pre-installed camera app.         |
| Speaker / Mic             |            ✅            |               |
| Bluetooth                 |            ✅            |               |
| WiFi                      |            ✅            |               |
| SIM / Mobile Data / Voice |            ✅            |               |
| VoLTE                     |            ✅            |               |
| Fingerprint               |            ✅            |               |
| NFC                       |            ❓            |               |
| Offline Charging          |            ✅            |               |
| Other features            |            ❓2            |             |
> 1 If you do not want blurry pictures, use a Google Camera [port](https://www.celsoazevedo.com/files/android/google-camera/). There will still be blurry previews though, only one camera is usable, and all pictures will be taken at 8 MP instead of 12/48 MP. Video mode is still all fine, though, you can record at 1080p@24/30/60fps just fine.


> 2 Vibration motor/mechanism is a bit wacky. Some games/apps that support gradual increase/decrease of vibration strength (e.g: Gboard) will either not activate vibration at all, or ALWAYS use maximum vibration strength. Strangely enough, weaker strength is still available, though only for navigation methods like gestures.

# **Additional Notes before bare-metal installation**:
* In order to install a GSI as a replacement to any existing firmware (be it stock or GSI), please do the following steps:
   1. Do the bootlocker unlock guide above (if you haven't already).
   2. Get into bootloader (achieved via holding down volume down + power buttons while rebooting)
   3. Run `fastboot -w`
   4. Reboot into `fastbootd` via `fastboot reboot fastboot`
   5. In `fastbootd`, flash the GSI via `fastboot flash system [INSERT FILE NAME OF DOWNLOADED GSI].img`
        * e.g: `fastboot flash system Elixir.img`
        * If `fastboot` throws any complaints about not having enough space to resize partition (especially if you're trying to install a GSI from stock firmware), try running these commands:
          ```fastboot
          fastboot delete-logical-partition product_a
          fastboot delete-logical-partition product_b
          ```
          and if it still complains about resizing, then run:
          ```fastboot
          fastboot delete-logical-partition system_a 
          fastboot delete-logical-partition system_ext_a
          fastboot delete-logical-partition system_ext_b
          ```
   6. Flash a `vbmeta` image (could be from the stock firmware, accessed via the Nokia OTA [Telegram channel](https://t.me/nokiarepoen). I personally used Google's official `vbmeta` image, however (can't find any links, sorry)) with the command: `fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img`
   7. Reboot with `fastboot reboot`.

---

**Tested by**:

VNGamerGit (a.k.a cherries [fumo | gentoo] or entropyonline_001 on Discord) - TA-1332, Vietnam region - V3.40/00WW_3_400 @ far too many days, this page was created in 14/4/2024 (dd/mm/YYYY), so...