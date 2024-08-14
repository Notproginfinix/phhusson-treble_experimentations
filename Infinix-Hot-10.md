# 📱 Infinix Hot 10 - x682b
Infinix Hot 10. Announced Sep 2020. Features 6.78″ display, MT6769V chipset, 5200 mAh battery, 128 GB storage, 6 GB RAM.

Important device info most people should know.

Device Info: ARM64, VNDK (Not Lite), A-only, Systen-as-root, No seamless Update

Hardware status summary or important caveats:

- Make a full dump as a backup beforehand via SoC (mtkclient works), this phone is really fragile and you'll most likely need to use BROM to recover every now and then
- You only can install a GSI that has an unzipped size of 2.6gb at max safely after erasing product (You should be able to erase system_ext too)

## 📃 Steps to install

* Unlock your bootloader
* Make a full dump as a backup (Optional, highly recommended incase you hardbrick. Check mtkclient for this)
* Get stock firmware that matches your current build number on settings (Or just get it from the dump earlier)
* Reboot to bootloader (fastboot) via combo or via `adb reboot bootloader`
* Disable verity and verification via `fastboot flash vbmeta vbmeta.img --disable-verity --disable-verification`
* Reboot to fastbootd via `fastboot reboot fastboot`
* If your GSI unzipped size is 1.4gb or lower, you can immediately flash it as system via `fastboot flash system example_arm64_gsi.img`
* If your GSI unzipped size is higher (1.6-2.6gb) and you get *Not enough space to resize partition* while flashing it, try `fastboot resize-logical-partition product 33500` (you can probably delete the logical partition it but I just resize it just to be safe)

## ⚙️ Hardware support

| Component                 | Status |      Comment                                              |
|---------------------------|--------|-----------------------------------------------------------|
| Camera                    | ✅    | ✓                                                         |
| Wifi                      | ✅    | ✓                                                         |
| Speaker                   | ✅    | ✓                                                         |
| Mic                       | ❔    | Untested                                                   |
| SIM / Mobile Data / Voice | ✅    | ✓                                                         |
| Bluetooth                 | ✅    | ✓                                                         |
| Offline Charging          | ⚠️    | Most likely Broken                                         |
| Speaker                   | ✅    | ✓                                                         |
| Speaker                   | ✅    | ✓                                                         |

<!-- 
It's best to include as many components as you can, especially device-specific features like flip-cameras, fans, folding, etc. 

Common components may include: Camera, SIM / Mobile Data / Voice, Speaker / Mic, Bluetooth, NFC, VoLTE, Auxiliary Cameras, Wi-Fi, Sensors.

People are not interested in what works, so put what doesn't work first.
-->

Tested By: @rubberhosehuman - x682b - Ver. 358
Page Created by: @baguubaguu

## ℹ️ Additional Notes

- System-as-root requires you to get an AB gsi, however since seamless-update is not present. The actual slots are actually a-only. Thus you can wipe `product` and `system_ext` rather than `product_a`, `product_b`, system_ext_a`, `system_ext_a`, `system_ext_b`, and the other system's slot. This limits us quite heavily.
- Note 2
- Note 3

### Tested GSIs
- [Android 11 AOSP](https://ci.android.com/builds/branches/aosp-android11-gsi/grid?)
- [LineageOS 19.1 Android 12](https://sourceforge.net/projects/andyyan-gsi/files/lineage-19.x/)
- [CAOS Android 10](https://github.com/eremitein/treble-patches/wiki/CAOS-Project)
- [phhusson Android 10 gsi](https://github.com/phhusson/treble_experimentations/releases/download/v222/system-quack-arm64-ab-gapps.img.xz)

---

Template created by @zguithues and @hackintosh5