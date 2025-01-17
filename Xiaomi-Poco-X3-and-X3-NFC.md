# Poco X3 NFC

Tested by [sadyqowl1560](https://github.com/sadyqowl1560) and [Piotr Marendowski](https://github.com/piotr-marendowski).

# Arm64, A/B, stock vendor:

## Installation

1. Unlock your phone via [Mi Unlock](https://en.miui.com/unlock/download_en.html) (requires an account).

2. Install firmware via [MiFlash](https://github.com/droidfirmwares/miflashtool/releases) tool which will have the same Android version as your chosen GSI e.g. MIUI 12.0 with Android 10 for Android 10-based GSI etc.

3. Install recovery that will support your target system[1]. Install it via fastboot `fastboot flash recovery twrp.img`.

4. Optional: Boot to recovery, backup what you can (specifically the `super` partition).

5. Enter `fastbootd`, and install the system image: `fastboot flash system system.img`.

6. Reboot to recovery, format data (otherwise it won't boot!).

7. Reboot to the system.

<br>

1. For example, I installed vanilla AOSP 10 via TWRP 3.5.2 with stock MIUI 12.0 Android 10. (Piotr)

## Bugs

- Audio issues. In phh settings, enable `Disable audio effects`, and `Use alternate audio policy`.
- Ghost touch. ~~Push [uinput-goodix.kl](https://del.dog/uinput-goodix.txt) to /system_root/system/usr/keylayout in recovery~~ (dead link). Fingerprint sensor is at fault here, there are solutions to this on the internet, but they require root. If you're not using fingerprint sensor, then you can seal it with a tape, which will almost fix this problem.
- Screen casting doesn't work - device reboots after connecting to TV.
- Sometimes screen color looks yellow (can't reproduce).
- Screen flickering in some gsi (can't reproduce).

Otherwise everything works perfectely (AOSP 10 phh vanilla).
 