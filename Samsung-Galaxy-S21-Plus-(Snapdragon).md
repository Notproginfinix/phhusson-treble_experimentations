## Steps to install
**THIS WILL ERASE ALL YOUR DATA**\
**AND VOID YOUR WARRENTY**\
**AND OBVIOUSLY TRIP KNOX (NO SECURE FOLDER, NO SAMSUNG PASS)**

### Unlock Bootloader
- Enable OEM unlocking and USB Debugging in developer settings
- Turn Off Your Device
- Boot into Download Mode (Press Up and Down Volume when Powered Off and Connect Cable to a Computer)
- Long Press Volume Up to Unlock Bootloader

### Install TWRP
- Download Required files
  - TWRP
  Images:\
    [SM-G996B, SM-G996BN](https://www.mediafire.com/file/mdqm3vrmkcghwov/twrp-3.7.0_11-2_afaneh92-t2s.tar/file)\
    [SM-G9960, SM-G996U, SM-G996U1, SM-G996W](https://www.mediafire.com/file/33gx48ett2yn9n8/twrp-3.7.0_12-1_afaneh92-t2q.tar/file)
  - VBmeta Verification Disabler \
    [All varients](https://www.mediafire.com/file/zuco6wfd9d8qldm/vbmeta_disabled_R.tar/file)
- Boot into Download Mode Again
- Open Odin3 (If you don't have Odin, get it from [OdinDownload](https://odindownload.com)) (Recommend v3.13)
- Put TWRP tar into AP, and VBmeta tar into USERDATA
- Press Start
- Boot back into One UI and Reboot into Recovery with `adb reboot recovery`
  - [ADB](https://developer.android.com/studio#downloads); install latest command-line tools for your system
  - [Samsung Android USB Driver](https://developer.samsung.com/android-usb-driver)
- Navigate to Advanced -> Terminal; enter `multidisabler`

### Installing GSI (through TWRP)
- Wipe data
- Factory Reset
- Clear Data + Cache + Dalvik/ART Cache
- Navigate to Advanced -> Terminal; enter `multidisabler`
- Reboot to Recovery Again
- Push the img image from your computer to the device
- Flash it as a `System Image`
- Reboot

### Brightness
- Go to Phh Treble Settings
- Select Samsung Features
- Press Set backlight scale/max backlight level
- Type `-1` in the dialog and press OK
and adjust the screen brightness on your phone

### Screen flickers
- Go to Phh Treble Settings
- Select Samsung features
- Enable option `Enable workaround for white-ish screen`
- Go back and select Misc features
- Enable option `Disable HW overlays`

### Enable Always-on-display
- Go to Phh Treble Settings
- Select Misc features
- Enable option `Force allow Always-On-Display`

## Hardware support

| Component                 | Status |
|---------------------------|--------|
| Camera                    | √ |
| Speaker / Mic             | √ |
| Bluetooth                 | √ |
| WiFi                      | √ |
| SIM / Mobile Data / Voice | √ |
| Brightness                | [*](https://github.com/phhusson/treble_experimentations/wiki/Samsung-Galaxy-S21-Plus-(Snapdragon)#Brightness)(Display is dimmed; Fix provided here) |
---

@litszwaiboris - 2024/05/20 (Updated:2024/07/16)