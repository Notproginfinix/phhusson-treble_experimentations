

# 📱 Samsung Galaxy A54 5G - a54x
<!-- e.g. Google Pixel 6a - bluejay -->

Quick Summary...

Device Info: arm64, System-as-root. 
<!-- 
Important device info most people should know.

Device Info (arch, VNDK support):

**System-as-root | VNDK Lite | ARM64**

Hardware status summary or important caveats:

- X doesn't work, but everything else does...
- Y might not boot if...
- Z breaks Y, so...

If someone maintains presets for your device, you can tell people how to apply those. https://github.com/TrebleDroid/treble_presets
-->

## 📃 Steps to install

* Install a custom recovery such as TWRP or OrangeFox. Alternatively you can patch your stock recovery with fastboot.
* Enter fastboot mode
* `fastboot flash system gsi.img`
* `fastboot reboot recovery`
* Wipe cache, dalvik
* Format data
* Reboot
<!-- 
Most modern devices follow the generic procedure using fastboot.

fastboot flash system system-arm64-aonly-gapps-su.img
fastboot -w
fastboot reboot

Include useful info! For example: what to do if the system image is too large.
-->

## ⚙️ Hardware support

| Component                 | Status |      Comment                                              |
|---------------------------|--------|-----------------------------------------------------------|
| Camera                    | Working   | <!-- Broken due to... -->                                    |
| Speaker / Mic             | Working   | <!-- See issue #24... -->                                    |
| SIM / Mobile Data / Voice | Working     | <!-- Untested... -->                                         |
| Bluetooth                 | Working
  120hz Refresh Rate | Working | Stutters sometimes if you have a PiP video playing<!-- If you enable... -->                                    |
5G | Untested | No 5G in my country
Fingerprint | Not working
Auto Brightness | Working
Offline Charging | Not working | Stays on charging loading screen
VoLTE | Untested | No VoLTE in my country
|Adaptive Refresh Rate | Working partially| Some apps (for example: YouTube) will keep the refresh rate at 120hz

<!-- 
It's best to include as many components as you can, especially device-specific features like flip-cameras, fans, folding, etc. 

Common components may include: Camera, SIM / Mobile Data / Voice, Speaker / Mic, Bluetooth, NFC, VoLTE, Auxiliary Cameras, Wi-Fi, Sensors.

People are not interested in what works, so put what doesn't work first.
-->
# Compatibility
- VNDKLite GSIs are NOT supported, you will end up in an infinite bootloop.
- Android 14 QPR1, QPR2 and QPR3 GSIs are supported.
- Android 15 GSIs are now supported as of December 1st, 2024

* Tested By: Pokey8680 - SM-A546B (Europe),
* Stock FW: A546BXXS9CXH7
* @ Tested on Oct 8 - Dec 1, 2024
# GSIs Tested
## Android 14
* [Andy Yan's LineageOS 21, November Build (QPR3)](https://sourceforge.net/projects/andyyan-gsi/files/lineage-21-td//)
* [Trebledroid CI Build](https://github.com/TrebleDroid/treble_experimentations/releases/tag/ci-20240508) 
* [Ponces' AOSP](https://github.com/ponces/treble_aosp/releases/tag/v2024.08.16)
* [Evolution X](https://github.com/mytja/treble_evo/releases)
## Android 15
- Ponces' AOSP