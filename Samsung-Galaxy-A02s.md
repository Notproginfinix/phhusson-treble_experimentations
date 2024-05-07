# Samsung Galaxy A02s

| Components | Status |
| --- | --- |
| Camera (FRONT/BACK) | WORKING ✅ / WORKING ✅ |
| Speaker/Mic (TOP/BOTTOM) | WORKING ✅ / WORKING ✅ |
| Bluetooth | WORKING ✅ |
| Wi-Fi | WORKING ✅ |
| SIM / Mobile Data / Voice Calls | WORKING ✅ /  WORKING ✅ / Partially works ✳️ |
| VoLTE | Unknown ❔ |
| Offline Charging | WORKING ✅ |
| Normal / Fast Charging | WORKING ✅ / WORKING ✅ |
| USB / USB OTG | WORKING ✅ / WORKING ✅ |

##### Terms used:

Patched recovery - Patched recovery made with the stock recovery patcher.

Custom recovery - TWRP, OFOX etc...

## Custom recoveries/kernels/vendors

- [TeamWin Recovery Project (Unofficial)(Discontinued)](https://t.me/galaxy_a02s/13051)
  
  - The developer has stopped updating it or abandoned it. However, It still functions as expected and has no bugs.
  - You can flash it through Odin, Heimdall or if you already have a custom recovery installed on the device, you can just flash the recovery.img file found inside of the .tar file as a recovery image.
- [Stock recovery Patcher (Click to know more)](https://github.com/engineer4t/fastboot-patcher)
  
  - You can use this to patch your stock recovery and add fastbootd to it. This will allow you to flash **only .img** files on it and should be enough for installing GSIs.
  - The patched recovery obtained can be flashed through Odin, Heimdall or if you already have a custom recovery installed on the device, you can just flash the recovery.img found inside the .tar file as a recovery image.
- [vbmeta-disabler](https://t.me/galaxy_a02s/13058) ****REQUIRED!****
  
  - This needs to be flashed through ODIN before installing a custom recovery and a patched recovery in order for the recovery to be able to run and also, to be able to run custom roms on your phone.
  - You can flash it only through Odin or Heimdall.
- [Smiley's ARM32(Binder)/ARM64 Custom vendor](https://t.me/samsung_galaxy_m01_a01_m11_a11)
  
  - The vendors have watchdog completely disabled and **allows GSIs that hasn't been updated at June 2023 or later**(or has been abandoned) to work on the device. See notes for Running GSIs below for more info.
    
  - ARM64 vendor is a ported vendor from M02s. Some things do not function properly on it and it has lots of bugs. However if you intend to use it only to run ARM64 games on the phone, then you can use it but do note that you might experience minor glitches and bugs on games.
    
  - This can be flashed only through a custom recovery such as TWRP or OFOX.
    

## Important notes

### Running GSIs

Any attempt in running a **secure** or **secure-on-demand**¹ GSIs that **hasn't been updated at June 2023 or later** will make the device hard reboot every 10-20 seconds after booting up. You might think that the GSI has booted properly but after some seconds, it will do it.

¹Only when you **securize** or you turn on **Device Spoof Properties.**

Same applies for when you try to use any Magisk module to fix SafetyNet such as Universal SafetyNet Fix. Basically, any method used to fix SafetyNet will cause the above issue. Properties are always spoofed on Secure GSIs so that's why the above issue happens.

Phh has fixed the above issue by changing the way how Watchdog and Watchdogd is handled by GSIs. You can apply these fixes on old GSIs using appropriate tools to unpack and repack the GSI or by using root. However, I would recommend you to use a newer GSI or just wait for developers to implement the fixes in their GSI.

No need to and you shouldn't turn on any **Alternate audio policy** option or any audio-related options in phh Treble options. This will break the audio system. However, disabling **sound effects in Qualcomm settings** or disabling **audio effect in Misc Settings** won't break it.

Not sure how the above option works. -- @mrugtangy

### How to GSI

#### Unlocking the bootloader.

- To be able to install GSIs and a custom ROM, you should first **unlock the bootloader**. **Do note that you can't unlock bootloader on some variants**!
  
- First, Enable the Developer's Settings in settings by tapping on the Build number several times in the About section (Basically how humans do it unless you're from Mars).
  
- Then, go to the Developer's Settings (Last setting on the home page of Settings) and you should see **OEM Unlocking** and **USB Debugging**. If you don't see the OEM Unlocking option, it might be because it's a carrier-locked one or maybe a variant that doesn't allow the unlocking of the bootloader.
  
- Enable both options and reboot to **Download Mode** by first, powering off your device, holding both **Volume UP and DOWN** button while plugging a USB cable to it that's **connected to your PC**. If you see a blue screen pop-up, it means that you've successfully booted into Download mode!
  
  If you see an option called Device Unlock Mode, this means that you can proceed further! Then, long press on the **Volume UP** and continue with the process!
  
  **NOTE THAT THIS WILL ERASE YOUR DATA SO TAKE A BACKUP BEFORE DOING SO!**(unless you don't care about your data or there's none). You can use the Smart Switch software on your PC to do it.
  
- After rebooting, complete the setup process, connect to a network, check for updates, enable developer settings again and if you see the OEM Unlocking option greyed out, it means that you have successfully unlocked the bootloader!
  
- After rebooting, boot back to download mode and flash the vbmeta disabler so that you're able to flash a custom or patched recovery and be able to flash GSIs
  

#### Choosing the right GSI and other stuff

A02s only supports **a64/arm32_binder64 - A/B** GSIs. So, make sure to only choose them.

If you're going to use the **ARM64 Vendor**, you should only use **ARM64 - A/B** GSIs.

If you're going to install Magisk, make sure to choose a GSI that **doesn't contain phh SU**.

SGSIs(Semi-GSIs) are not guaranteed to work perfectly on it. So, use them at your own risk!

#### Installing a GSI

Before installing a GSI, make sure you have a **custom recovery** or have installed a **patched recovery**(tool found above). The fastboot option that's found on the stock recovery (basically the one that says reboot to bootloader in stock recovery) is completely useless so you shouldn't be using that.

After installing any of them, you'll be able to flash a GSI by either:

- Flashing it as a system image in a **custom recovery** using methods such as sideload or by having the image on an SD card that's on the phone. You can also plug a USB drive through OTG with the image on it.
  
  or
  
- By flashing it through fastboot on a **custom recovery** or a **patched recovery**(recommended) using the following commands:
  
  To flash a GSI :
  
  ```bash
  fastboot erase system # To erase the system partition
  ```
  
  ```bash
  fastboot flash system <your gsi img> # To flash your GSI
  ```
  
  To empty out the product partition (Optional) :
  
  ```bash
  fastboot erase product # To erase the product partition
  ```
  
  ```bash
  fastboot flash product product_gsi.img # To flash an empty product image
  ```
  
  [product_gsi.img](https://forum.xda-developers.com/attachments/product_gsi-img.5371179/) - click to download
  
  However, if you're using another phone to do that (through OTG) then the above drivers won't be required.
  
  Then, reboot to the recovery by either pressing on reboot system if you use a **custom recovery** or just select the option to go back to the recovery if you're on a **patched recovery**.
  
  After that, clear data by going into the Wipe options in **TWRP** and pressing Advanced Wipe and selecting **Data, Dalvik, Internal Storage and Cache**.
  
  If you're on the **patched recovery**, you should use **Wipe data** and **Wipe cache** options to wipe the data and cache.