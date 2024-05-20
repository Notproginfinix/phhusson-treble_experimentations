## Steps to install
**THIS WILL ERASE ALL YOUR DATA**

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
- Open Odin3 (If you don't have Odin, get it from [OdinDownload](https://odindownload.com)) (Recommend v13)
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

## Fix Brightness (Requires Root)
- Connect to a computer
- `adb shell` into the device
- `su` to use shell as superuser
- Type either \
`setprop persist.sys.qcom-brightness -1` \
`setprop persist.sys.qcom-brightness 255` \
`setprop persist.sys.qcom-brightness 4095` \
and adjust the screen brightness on your phone

## Hardware support

| Component                 | Status |
|---------------------------|--------|
| Camera                    | √ |
| Speaker / Mic             | √ |
| Bluetooth                 | √ |
| WiFi                      | √ |
| SIM / Mobile Data / Voice | √ |
| Brightness                | [*](https://github.com/phhusson/treble_experimentations/wiki/Samsung-Galaxy-S21-Plus%20%28Snapdragon%29/##Fix%20Brightness%20%28Requires%20Root%29) |
---

@litszwaiboris - 2024/05/20