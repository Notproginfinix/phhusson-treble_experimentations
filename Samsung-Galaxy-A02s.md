# Samsung A02s (SM-A025F, SM-A025G, SM-A025M)

## Custom Recoveries/Kernels/Vendors:

TWRP (Unofficial): [Click here](https://forum.xda-developers.com/t/recovery-unofficial-twrp-for-galaxy-a02s-snapdragon.4294377/)

OrangeFox (Unofficial)**(Discontinued)***: [Click here](https://forum.xda-developers.com/t/recovery-unofficial-twrp-for-galaxy-a02s-snapdragon.4294377/)

ARM32(Binder)/ARM64 Custom vendor: [Telegram](https://t.me/samsung_galaxy_m01_a01_m11_a11)

Stock recovery Patcher (Adds Fastbootd to stock recovery) : [Click here](https://github.com/tangymc/Patch-Recovery)

***VERY UNSTABLE AND DOESN'T WORK! USE TWRP!**

## NOTES (VERY IMPORTANT!) :

### About the custom vendor :

As the device has a binder arch, an arm64 custom vendor was created to add arm64 support on the device. But do note that the custom vendor is very unstable and some things such as fast charging do not work on it. Has **watchdog disabled** which allows the usage of old or outdated GSIs without modifying anything.

Binder vendor has **watchdog disabled** which allows the usage of old or outdated GSIs without modifying anything. 
Both custom vendors have **SELinux set to permissive**.

### About choosing the right GSI image :

Use binder GSI images for **stock vendor and ARM32(binder) custom vendor**! Binder GSI images will either be marked as **a64** or **arm32_binder64**.

If you're using **ARM64 custom vendor**, use arm64 GSIs only. arm64 GSIs will be marked as **arm64**.

Some images might have **A/B(ab)** or **A-only** variants. Use **A/B(ab)** ones.

### Flashing a GSI image (**Custom or patched** recovery is required) :

Either flash it as system image on your custom recovery (make sure it's a .img file).

or

Use fastboot to flash the image by using the following command(recommended)

`fastboot flash system <your gsi img>`

Note that you shouldn't erase data using fastboot as this will **brick the partition**. Use the **Format Data** option in your custom recovery or **Wipe Data** on the patched recovery to do it.

### Erasing the product partition (**Custom or patched** recovery is required) :

First, do `fastboot erase product` and then, flash the [product_gsi.img](https://forum.xda-developers.com/attachments/product_gsi-img.5371179/) by doing `fastboot flash product product_gsi.img`. 

### Installing Magisk on GSI images.

- Download the Magisk APK from the following [repo](https://github.com/topjohnwu/Magisk) in releases.
  
- In TWRP, Go to Install and select the APK and flash it.
  

OR

- De-lz4 your boot.img.lz4 found in your firmware's AP using appropriate tools and you should obtain a boot.img file.
  
- Install the magisk app on a phone regardless if it's rooted or not.
  
- Click on install and select Patch a file and select the boot.img file.
  
- After it's done, transfer the patched boot.img (might be found in Downloads) to your PC
  
- Flash the boot image by doing `fastboot erase boot` and then `fastboot flash boot <your patched boot image>`
  

If you want to make system files R/W on root, use **VNDKLITE** GSIs or [this magisk module](https://github.com/Magisk-Modules-Alt-Repo/magisk_overlayfs).

Note that magisk should only be installed on non-superuser GSIs. See [this](https://github.com/phhusson/treble_experimentations/wiki/Frequently-Asked-Questions-%28FAQ%29#naming-conventions-that-some-gsi-buildermaintainer-uses) to be able to identify which image is non-superuser.

### Important things if you're going to use any old release of/outdated GSI (applies only to stock vendor) :

#### About old/outdated GSIs :

Old/Outdated GSIs means that it hasn't been updated at **June 2023 or later**.

#### What won't function properly and why :

- Secure GSIs will crash after some secs due to watchdog issues.
  
- Secure-on-demand GSIs will crash after some secs if you enable **Spoof Device Properties** due to watchdog issues. But you'll have approximately 20-30 secs to turn it off before it crashes.
  
- Using any magisk module such as Universal SafetyNet Fix to pass SafetyNet on a magisk-rooted device will make the GSI crash due to watchdog issues.
  
- Alternate Audio Policy cause issues such as not being able to change volume and volume stays always on 100%.
  
- Call audio doesn't work
  

#### Fixes that phh has implemented for that (which has been added in new and new releases of GSIs) (according to [this commit]()) :

- Removed the script that disables watchdog from rw-system.sh.
  
- Added a script that pings watchdogd in vndk.rc.
  
- Partially fixed call audio in another commit
  
  - Note that call audio only works on SIM 1 and doesn't work on SIM 2. However, this won't be an issue if you have a single-sim device.
    

#### Implementing that fix if you're going to use an old GSI :

Replace **rw-system.sh** (found in /system/bin) and **vndk.rc** (found in /system/etc/init) in your GSI by either :

- Unpacking, replacing the files and repacking the GSI Image using appropriate tools.
  
- Replacing the files on a phone that has magisk installed(rooted with magisk). This requires a R/W system. See notes above on how to make your system R/W.
  

Make sure to set the appropriate permissions after replacing the files.

**For the call audio fix, use the fix made by smiley on the Telegram channel of the custom vendor found above.**