# 📱 Realme 8 Pro - RMX3081

**System-as-root | Full VNDK | ARM64**

Most basic features work perfectly, but some hardware/software components are broken. Most minor issues can be automatically fixed by connecting to the internet and doing: 

* Treble Settings → My Device → Apply Presets.
* Treble Settings → IMS → Install APK for Qualcomm Vendor.
* Reboot.

RMX3081 comes with the 4.14 kernel version, so don't expect most initial A14 QPR2 releases to boot.

## 📃 Steps to install

**Back up `super` before proceeding!**

Flash your image with the `fastboot` utility from `platform-tools`:

```
fastboot flash system system-arm64-ab.img
```

Do NOT wipe data through TWRP, PBRP or OrangeFox, use `fastboot -w` instead. If the ROM is too large to install, you can delete some `my_*` partitions to free more space. Do note, that deleting some partitions can lead to a boot loop. Unlike other devices, the `product` partition on the 8 Pro is tiny (12MB), so it's not worth removing it.

```
fastboot delete-logical-partition my_preload
```

## ⚙️ Hardware Support (Android 14)

| Component                 | Status | Comment                                           |
|---------------------------|--------|---------------------------------------------------|
| Biometrics (FOD & Face)   | ❌ | [Issue #39](https://github.com/TrebleDroid/treble_experimentations/issues/39). Multiple A14 ROMs include ParanoidSense to support face unlock  |
| Light Sensor              | ❌ | [Issue #32](https://github.com/TrebleDroid/treble_experimentations/issues/32) |
| NFC                       | ⚠️ | Crashes after scanning unknown tag types              |
| Offline Charging          | ❔  | Broken in F.9, might be fixed in F.10                 |
| Auxiliary Cameras         | ❔  | Untested                                              |
| VoLTE                     | ✅ | After installing IMS.apk from Treble Settings         |
| Main and Front Cameras    | ✅ |                                                       |
| Speaker / Mic             | ✅ |                                                       |
| Bluetooth                 | ✅ |                                                       |
| WiFi                      | ✅ |                                                       |
| SIM / Mobile Data / Voice | ✅ |                                                       |
| Other Sensors             | ✅ |                                                       |
---

Tested By: melontini - F.9 | Android 14 QPR2 @ 05/2024

## ℹ️ Additional Notes

- DT2W and [DC Dimming](https://github.com/TrebleDroid/treble_experimentations/issues/106) do not work.
- LTE might not be selected as the default network type. Simply change that in the SIM menu.
- ZRAM is disabled by default and must be enabled manually. (Stock is configured using the `product/bin/init.oplus.nandswap.sh` script)

***

Template created by @zguithues and @hackintosh5