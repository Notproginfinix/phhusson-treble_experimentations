Doing something on this device can be quite challenging, so this is a small guide for those who want to change something

# İnstall GSI and some informations

First, let's give the device information (same result for everyone);
- Codename: `tb8765ap1_bsp`
- Model code: `8088X` (global variant. I have this)
- VNDK version: `28`
- Android: `9`
- AVB: `true`
- AVB Version: `1.0`
- System partition size: `2.5GB` (This also means the maximum GSI image size)
- Processor: `MediaTek MT8765WB`
- Processor platform: `MediaTek MT6739` (the two are like copies of each other)
- Partitions: `A/B` (only one partition)
- Arch: `arm-32 (32-bit)`
- GSI Variant: `system-arm32-binder64-ab` (A64)
- DM-Verity: `of course`

### Some important notes (please read):
- There is no `vbmeta` partition on this device. DM-Verity and AVB related stuff is in `seccfg` (`bootloader`).
- There are some variations of this device. For example, like the European version. To explain with model code: EEA ROM: `8088X_EEA` Global: `8088X`. I think it was self-explanatory.
- I definitely recommend backing up some partitions before handling the device. Partitions: `boot recovery seccfg nvdata nvram nvcfg persist protect1 protect2 vendor system`
- A color problem occurs on this device on Android 12.1 and above. [Check out this post](https://github.com/TrebleDroid/treble_experimentations/issues/91)
- These are what I remember for now

### GSI selection and prepartions
1. First, install the [Treble İnfo](https://play.google.com/store/apps/details?id=tk.hack5.treblecheck) application. And check everything. It should be the same as what I gave above.

2. Download a compatible GSI image of your choice from the [Treble list](https://github.com/phhusson/treble_experimentations/wiki/Generic-System-Image-%28GSI%29-list) (it's the safest and best). There are not many options from new versions for this device. As I said above, only use Android 12.1 and below. Of course, if you want, you can try higher ones and let me know the result. You can learn about some symbols by [clicking here](https://sourceforge.net/projects/andyyan-gsi/files/). See namına tules. (For example, like bvN)

3. What you download should most likely be an `xz` archive. To debug this using linux terminal or termux: `xz -d <file_name>`. You can use 7zip and similar programs to extract on Windows. If you are using Linux or Windows, place it inside the folder where the fastboot binary is located.

4. We need to download other necessary things. For example, like drivers (Windows). Installing MediaTek and Google drivers will be enough. In Linux, installing `libusb` is sufficient. And of course platform-tools. If you are using Bugjaeger, do not forget to install it.

## Flashing
It would be best to use a Windows or Linux computer to do this. Or you can use Bugjaeger App using OTG.

1. Enable developer settings on the tablet. And enable USB debugging. And change the default USB configuration to file transfer. (If you are going to use OTG, do these operations on the device where flashing will be done)

2. Connect the device to the device that will flash. Make sure you know him.

3. Turn off the device. Press and hold volume up + power button. Select fastboot from the menu that appears.

4. If you have put it in fastboot mode, now reconnect the device. Make sure it's visible.

5. Open fastboot. Those who use Bugjaeger can find it by going to the '⚡' section. Windows users can just go to the folder where the binaries are located.

Commands:
```
fastboot erase system
fastboot flash system <file>
fastboot -w
fastboot reboot
```
If you are using Linux, execute the commands as root (sudo) and using `./`
That's all there is to it. In the <file> section, if you are using Linux or Windows, you need to write the file name or path. If you are using Bugjaeger, you can select it by pressing the file selection button.

### Problems and solutions
- You tell us, let's think.
- I will have answers to most of them, because I have tried almost all compatible GSI images on the list.
