# 📱 Xiaomi Redmi K70 Pro - Manet

**⚠️ This page is work-in-progress**

| Device Info    |               |
|----------------|---------------|
| Name           | Redmi K70 Pro |
| Codename       | `Manet`       |
| Architecture   | ARM64         |
| System-as-Root | Yes           |
| VNDK Lite?     | No            |

<!-- 
Important device info most people should know.

**System-as-root | VNDK Lite | ARM64**

Hardware status summary or important caveats:

- X doesn't work, but everything else does...
- Y might not boot if...
- Z breaks Y, so...

If someone maintains presets for your device, you can tell people how to apply those. https://github.com/TrebleDroid/treble_presets
-->

## 📃 Steps to install

* Unlock the bootloader
* Grab the `vbmeta_system.img` of your current install. (You can find stock firmware archives [here](https://mifirm.net/model/manet.ttt))
* Reboot into fastboot (Hold Volume Down + Power when the device is off)
* Flash using the following commands:

```sh
fastboot flash --disable-verity --disable-verification vbmeta_system_ab vbmeta_system.img
fastboot reboot fastboot
fastboot erase system
fastboot delete-logical-partition product_a
fastboot delete-logical-partition product_b
fastboot flash system system.img
fastboot -w reboot
```

DO NOT flash `vbmeta`, only do `vbmeta_system`.

<!-- 
Most modern devices follow the generic procedure using fastboot.

fastboot flash system system-arm64-aonly-gapps-su.img
fastboot -w
fastboot reboot

Include useful info! For example: what to do if the system image is too large.
-->

## ⚙️ Hardware support

ToDo...

<!--

| Component                 | Status |      Comment                                              |
|---------------------------|--------|-----------------------------------------------------------|
| Camera                    | ❔     |      Untested...                                          |
| Speaker / Mic             | ❔     |      Untested...                                          |
| SIM / Mobile Data / Voice | ❔     |      Untested...                                          |
| Bluetooth                 | ❔     |      Untested...                                          |

-->

<!--

## ℹ️ Additional Notes

- Note 1
- Note 2
- Note 3

-->

<!-- Additional information that some people might find useful or non-critical issues.

- X feature doesn't work...
- Y might be disabled if...
- Install Z if you want...
--> 