# Installing GSI on a Samsung Galaxy A12s (Exynos)

## Here is what you need:

- [Super Patch](https://github.com/SUFandom/super-patch)
- [Termux APK](https://github.com/termux/termux-app/releases/latest)
- Samsung A12 Exynos Firmware AP 
- A capable ARM64 Android Device with 8 cores and 4GB of RAM
- Magisk Kitsuned Device (Previously called Magisk Delta) - This is important to not loop back to download
- A reliable Internet and data cable
- Trusty ODIN ready to work
- Physwizz TWRP v5 (For U9, UA, and UB devices) which you can get it on telegram, also for older ones, go to [Exynos 850 Development and Testing Group](https://t.me/a12schat)
- ZArchiver on Google Play
- Laptop that has Intel Core or AMD Athlon or Ryzen (Celeron, Pentium, and Intel N works, but ill label them unreliable to handle multitasks and processing)
- GSI with VNDKLITE (for Zygisk)

## Explaination

We are attempting to patch super file to install GSI, as doing the TWRP way wont work, `fastbootd` only works on a very few select handsets, some were successful at installing using fastbootd but few lost their IMEI

## WARNING!!!

If you have successfully installed a GSI, **DO NOT INTERACT WITH PHH TREBLE SETTINGS**, It can cause bootloops, so even if there's no sensor support on the GSI or even VoLTE issue, DO NOT INTERACT WITH PHH Treble Settings, just go download mode and flash another GSI, best to check the Charts below about issues and problems of GSI that works in this particular unit

## Instructions

### A. Patch

1. First copy this code snippet

```
cd ~ && apt update && apt upgrade && apt update && apt install git curl dialog -y && git clone https://github.com/SUFandom/super-patch
```

2. Elevate Permissions of the script to executable and run
```
cd super-patch && chmod +x *.sh && ./builder.sh
```

3. There will be some initialization, after that a disclaimer may pop up, read it and press sure

4. This is the menu were working with it, remember your Target dir

![image](https://github.com/phhusson/treble_experimentations/assets/70519093/1815090f-78bd-4586-bb56-eaf214555f07)

*The target dir mentions where the building takes place, the screenshot sample just shows the WSL directory, for android it would be `/data/data/com.termux/files/home/storage/image_build` which basically means your `/storage/emulated/0/image_build`* (Right now, running my script in WSL is not recommended temporarily)

5. Copy the super.img.lz4 from your magisked AP to the `image_build` dir in /storage/emulated/0

6. Head to Extract AP/Super then you will see this menu

![alt](https://github.com/SUFandom/super-patch/blob/main/media_md/img/image_1.png)

Select Extract Super

7. After that, you are prompted to select where is the GSI you want to install, ignore that because its still has bugs temporarily, wait for the next few updates, just go back

8. On Zarchiver, head to image_build, then delete system.img and product.img, those two contains OneUI files so to actually make the GSI working, those two needs to be gone

9. After that extract the GSI thats proven to work, table very below in this wiki

10. Rename the img to system on the image build dir

11. Go back to termux, then go Build Super

![img](https://github.com/SUFandom/super-patch/blob/main/media_md/img/image3.png)

12. then select build, then select sure

13. Wait for it to finish

14. The script may prompt you to rename the file, go ahead and name it, but do not add spaces and do not add extensions

![img](https://github.com/SUFandom/super-patch/blob/main/media_md/img/image_4.png)

15. After that , the super tar is ready

### B. Flashing it

1. Copy the file tar from image build dir to the PC

2. Ready the ODIN and some Magisked AP just in case

2.1 If your device isnt loaded with TWRP, i suggest do that first, head to the telegram group 

3. Mount the custom super file to AP on ODIN with Auto reboot disabled (IMPORTANT) and NAND erase enabled (ALSO EXTREMELY IMPORTANT)

4. Set device to download mode and plug the device to the PC

5. Start! and wait odin to say PASS!

6. after ODIN says pass!, hold vol down and power to reboot to recovery, it may bootloop once and thats normal

### TWRP

1. After its done bootlooping, go TWRP main menu > Wipe > Data > change file system > ext4 > then reboot to recovery

2.1. after that Main menu > Advanced > Terminal > type multidisabler twice > reboot to recovery > main menu > wipe > change file system of data >  set to f2fs > reboot to recovery again (to disable FBE, but if you want FBE, read 2.2)

2.2. after that Main menu > Wipe > Data > change file system > f2fs > reboot to recovery


3. After that wipe Dalvik cache and /cache then reboot to system


**AND THERE YOU HAVE IT!**


## Problems

If you have issues, talk to us: https://t.me/a12schat

## Supported GSIs for A12 Exynos

Table Updated: `Dec 21, 2023, 2:06PM: GMT 8+`

| GSI's                                                            	| Barely works with basic use cases 	| With Zygisk Running      	| Hardware/Software issues/features                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     	| Performance                                                                                                                                                                                                                   	| Kernel Recommendations          	|
|------------------------------------------------------------------	|-----------------------------------	|--------------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|---------------------------------	|
| Lineage Light 20 Gapps and non-Gapps                             	|                 ✔️                 	|             ✔️            	| Call intercept not working (which means you cant receive calls)<br><br>Fix: Set this on build prop: `persist.vendor.audio.fluence.voicecall` to either true or false<br><br><br>Only One camera Main module works<br><br><br>Android Not certified warning, Fix is to certify it here: https://google.com/android/uncertified                                                                                                                                                                                                                                                                                                                                                                                                                         	| War Thunder Mobile Reaching 40-60FPS (Low Graphics)<br><br><br>Genshin at 30-40 fps Low Graphics (stock usually at 20)<br><br>Blue Archive at 60FPS With Anti-alias                                                           	| Either stock or Physwizz Kernel 	|
| Pixel Experience Plus and Non plus (VNDK and VNDKLITE) by ponces 	|                 ✔️                 	| ❌ - will cause bootloops 	| Any zygisk enabled kills GSI to bootloop<br><br>Only one camera main module works<br><br>Any minimal interaction with phh settings or just barely navigating also bootloops<br><br>Audio Volume is weak, Configurations are located at phh settings but also bootloops, suggest download Flat Equalizer: https://play.google.com/store/apps/details?id=com.jazibkhan.equalizer&hl=en&gl=US (Works 99% all apps + NO ROOT Required) just turn loudness on and set value or Grab ViperFX, install modules and apk, then turn on master and raise the output limit (May not work on other apps)                                                                                                                                                          	| Takt Op. Symphony Surf around 21-25 FPS at Max<br><br><br>Genshin at 28-35 fps<br><br><br>War Thunder Mobile only 32-44 (Low Graphics)                                                                                        	| Physwizz Kernel                 	|
| Derpfest Android 14                                              	|                 ✔️                 	|             ✔️            	| CPU Util while on energy_step is laggy ( Fix is to set CPU Freq. Minimum at 546, or set CPU Governor at schedutil, performance is okay but its better to set it to schedutil for battery)<br><br>2 out of 4 Camera (wide angle, main) works except macro and B/W<br><br>Fingerprint scans way too sensitive <br><br>Any Minimal Interaction with phh settings or just barely navigating also bootloops<br><br>Unnecessary wakes, fix is disable waking gesture ( This was enabled by default)<br><br>Volume bar goes in the middle of the screen, fix is to just rotate screen, this event is rare so not much of a problem<br><br>Vietnam A12 Exynos Devices reported to have lost their IMEI, potentially due to A2DP, no fix has been confirmed... 	| Takt Op. Symphony hits around 39FPS low, in battle somehow, it drops to 12 fps low (Vulkan Issue)<br><br>Genshin Impact untested yet<br><br>War Thunder Mobile surfs around 33-46 (Low graphics)<br><br>Baseball 9 - 43-60FPS 	| Physwizz Kernel                 	|
| Miku UI 14                                                       	|                 ✔️                 	|             ✔️            	| Animation makes the UI feel laggy, fix is to turn on Dev Ops at the second part of Main Settings menu > Go way down then tap Build N., then go to the Animation, set to 1x all<br><br>There may be some hidden SU tools that i couldn't find (but found by magisk) so i would not recommend to daily drive on since idk what tools also preinstalled hidden                                                                                                                                                                                                                                                                                                                                                                                           	| NO DATA (SOMEONE CAN SUBMIT WITH VIDEO EVIDENCE)                                                                                                                                                                              	| Stock or Physwizz Kernel        	|
| PixelOS 13                                                       	|                 ❌                 	|             ❌            	| DIDNT WORK, STUCK AT BOOT, GSI PROBLEM                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                	| NO DATA                                                                                                                                                                                                                       	| NO DATA                         	|
| cRDROID 13                                                       	|                 ❌                 	|             ❌            	| BOOTLOOPING                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           	| NO DATA                                                                                                                                                                                                                       	| NO DATA                         	|
| PixelOS 14                                                       	|                 ✔️                 	|            TBA           	| Phh Settings Bootloops device                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         	| TBA                                                                                                                                                                                                                           	| TBA                             	|
| Evolution X (14)                                                 	|                 ✔️                 	|             ✔️            	| Phh Settings Bootloops device<br><br>Bugs from DerpFest 14 about volume still persists, but in the left now<br><br>It has a HyperV samsung, so that means you can do freeform windows<br><br>The CPU info may report XXXXX Degrees celsius, activate the Show CPU info on Settings > The Evolver > Misc > Scroll down > Show CPU info<br><br>Fingerprint and facial works <br><br>Only one out of 4 camera modules are usable, you cant do wide lens nor HDR Properly<br><br>IMEI reportedly wont work on Syrian A12s                                                                                                                                                                                                                                 	| War Thunder at 40-60fps<br><br>Genshin Impact - TBA<br><br>Takt Op. Symphony - TBA<br><br>Blue Archive - TBA                                                                                                                  	| Physwizz Kernel                 	|

## Prebuilt Super Images

Here are prebuilt images that will work on Exynos 850 A127 UA (128GB, 4GB RAM)

https://terabox.com/s/1kHhDYta9zdd8IwhwvmkxuA

### Always remember:

- Most GSI may not work unlike other android devices 
- If you did the steps right and still not booted, its a GSI problem
- There may be split archives in the host link, download all 7z files to extract super tarfile