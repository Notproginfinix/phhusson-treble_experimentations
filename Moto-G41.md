Works with [RisingOS](https://sourceforge.net/projects/risingos-official/files/3.x/) by UniversalX
# Hardware Support

| Component                 |      Working?                                             |
|---------------------------|-----------------------------------------------------------|
| Camera                    | ✓                                                         |
| Speaker / Mic             | ✓ (Needs extra config for JACK connections) (some GSIs have a broken call feature, fix below)              |
| Bluetooth                 | ✓                                                         |
| WiFi                      | ✓                                                         |
| SIM / Mobile Data / Voice | ✓                                                         |
| VoLTE                     | ? (Needs further testing)                                 |

# Bootloader unlocking

(I will include everything you need to do, if you already made some steps, just skip them) THIS STEP REMOVES YOUR WARRANTY, PLEASE BE CAREFUL IN THIS STEP, AS YOU CONTINUE DOING THESE STEPS, YOU ARE RESPONSIBLE OF WHAT YOURE DOING!

## Granting OEM unlocking and debugging options: 
Our first step is activating the OEM option in our motorola, go to "About device" we will go all the way down where it says "Build number" here, you will need to press this option quicly until either a message appears telling you that you're a developer now, or it requiring our unlocking method, do it, it could be a PIN, a password, or just a pattern.
Now we will get back to the system config, go all the way down and tap "System" here, you should find a good looking "Developer options" settings, *tap it*, now search the option "OEM unlocking", and *enable it*, our last step is to go a little bit down, here, you should find the "USB debugging" option, also enable it.
## Installing everything we need in our computer: 
I have two options on your desk: Windows and Linux, and we will see how to install everything we need for everyone:
### Windows installation:
Here, you should go to the [ADB tools](https://developer.android.com/tools/releases/platform-tools), choose the windows option, run the installer and wait until it finishes.
Now, you **should** intall the drivers, so we dont have trouble with fastboot commands, follow the steps according to your windows version: https://developer.android.com/studio/run/oem-usb
### Linux installation:
Depending from your distro, you have some or other ways to install it:
 * `sudo apt install adb` [On Debian, Ubuntu and Mint]
 * `sudo yum install adb` [On RHEL/CentOS/Fedora and Rocky/AlmaLinux]
 * `sudo emerge -a dev-util/android-tools` [On Gentoo Linux]
 * `sudo apk add adb` [On Alpine Linux]
 * `sudo pacman -S android-tools`[On Arch Linux]
 * `sudo zypper install adb` [On OpenSUSE]
## Booting fastboot with ADB tools and unlocking:
Here you will need to open your CMD or open your terminal and we are going to do some steps, finally unlock our bootloader.
* Type `adb reboot bootloader` and wait until it reboots.
* Go to the official [Motorola unlocking website](https://en-us.support.motorola.com/app/standalone/bootloader/unlock-your-device-b) and follow the steps. 
Done! you have succesfully unlocked your device! Next steps...
# GSI installing
The moment has come.
## Unzip your GSI and flash your system.
Open a CMD or terminal where your system.img from your GSI is, then, execute `adb reboot fastboot` in this mode, we have more controll with our motorola, so we can install everything we want (BE CAREFUL! THIS STEP REMOVES ALL YOUR DATA, CONTINUE WITH YOUR OWN RISK.) (note that you can't flash higher that 4GBs of GSIs, I need further research in this topic, so please be patient):
* Type `fastboot delete-logical-partition product_a`, hit enter and type `fastboot delete-logical-partition product_b` and hit enter.
* Type `fastboot flash system_a (system name).img` it is normally `system.img` but some other GSIs have its own system name.
* On your phone, with the volume and power buttons, go to recovery, hit power and hit wipe data, now, press "yes".
* Last step: hit "Reboot to software".
Done!
# Audio issues
When having headphones or headsets issues, go to config and somewhere here you should find "Phh Treble Settings" hit there, tap on Misc features, and hit on the "Audio" topic: "Use alternate way to detect headsets"
When having call issues, go to Phh Treble Settings and go to Misc, telephony and enable "disable "voice call in" route"
# PHONE BOOTLOOP FIX
I made some mistakes lol, so theres a fix:
* When your motorola is bootlooped, you can enter to the bootloader but not fastboot and obviously, the device gets a bootloop, well THERES A FIX!
i just found that by just typing ` fastboot flashing get_unlock_ability` you can get, well, the flash ability, i flashed the wrong boot.img when trying to root mine, so mine got bricked, you can fix this with yours, if you flashed, idk, the wrong vbmeta image, you can type this command, and then type `fastboot flash vbmeta (correct vbmeta image)`.

_Kroe Sufos_
Edited by:
* your name here and what changes youve done