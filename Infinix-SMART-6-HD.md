# 📱 Infinix SMART 6 HD - codename n/a
- CPU arch: ARM32
- Binder arch: 64-bit
- System-as-root, Seamless upgrades: yes
- Dynamic partitions: yes
- VNDK Lite: no

## 📃 Steps to install

1. Download [Andy Yan's LineageOS 18](https://sourceforge.net/projects/andyyan-gsi/files/lineage-18.x/) (use the boS one if you want Google apps, bvS from this one or newer versions if you don't) and extract it
2. Reboot phone to fastboot: `adb reboot fastboot`
3. Erase system: `fastboot erase system`
4. Flash GSI: `fastboot flash system /path/to/gsi.img`
5. Erase userdata: `fastboot -w`
6. Reboot: `fastboot reboot`

## ⚙️ Hardware support

| Component                 | Status |      Comment                                              |
|---------------------------|--------|-----------------------------------------------------------|
| Camera                    | ✅     |  Working                                                        |
| Speaker / Mic             | ✅     | Working                                                           |
| SIM / Mobile Data / Voice | ❔     | Untested                                           |
| Bluetooth                 | ✅     | Working                                                           |
| Flashlight                | ✅     | Working, but only way to use front flashlight is with camera flash |
| Face unlock               | ❌     | Unavailable |

Tested By: User8395 - X6512, Android 11 @ 6/9/2024

## ℹ️ Additional Notes

- Newer Android versions work too, but Android 11 is the only way to get Google apps as this phone only supports Google Go apps and has a small system partition that won't fit the standard Google apps.
- TWRP is unavailable, and zip flashing is unavailable if they are not signed.
- Internet does not work in Android 14 and 13. Any attempts to access a website will be met with the error `ERR_NAME_NOT_RESOLVED`. Older versions work fine.
- If you install the Google apps image, you will get a notification from Google Play Services complaining about Play Protect Certification. Follow the instructions [here](https://www.google.com/android/uncertified/) to eliminate it. You will have to do this after every factory reset.
- You must use fastbootd to flash the GSI instead of standard fastboot (bootloader). If you try to flash the GSI from standard fastboot, the phone will give the error "This partition does not exist".
- During my testing, Chrome was unable to download APK, and capped out at 100% without finishing.
- Downloading bvS, boS, or bgS versions of the GSIs will give you phhusson's superuser. Use bgN or bvN if you don't want it.
- This is not an extensive test, you are free to test some other stuff and ping me in a discussion with the results.