## Warning: The only GSI that worked on the Samsung Galaxy S23 is LineageOS 20 by Andy Yan
with other SystemUI crash.
Is possible to fix with a kernel optimized for GSIs

### How to install:

## **Unlock the bootloader**:
Open settings, go to about device, go to Software information and press build number 5 times, go back and press Developer options, developer options enable OEM Unlocking.
Shutdown the phone, connect a cable and press volume up and volume down.
after showing the download mode long press volume up after a message to unlock the bootloader and press volume up
setup again the phone and re-enable the OEM Unlocking, shutdown the phone, press volume up and volume down and after the download mode splash screen click volume up

## Flash the TWRP

Download Odin3 from https://odin-samsung.com/odin-3-14-1-official-latest-odin-download-zip-file-in-2020.html
Extract the zip file in a folder and run Odin3.

Download the TWRP Recovery and vbmeta_disabled_R.tar in https://forum.xda-developers.com/t/recovery-unofficial-twrp-for-galaxy-s23.4558749/

Now Open Odin and in AP select the TWRP file, in USERDATA select vbmeta_disabled_R.tar. click start and reboot your phone in TWRP 

## Flash the GSI
Download the GSI in my case i use LineageOS 20 by Andy Yan https://sourceforge.net/projects/andyyan-gsi/files/lineage-20-td/
in TWRP click Wipe, click Advanced Wipe and wipe Dalvik / Art Cache, Metadata, Data, Internal Storage and Cache and Swipe now go back and click reboot and reboot to fastboot, download android tools and with command promot type fastboot flash system "GSI's directory"
wait the flash and reboot 
Enjoy

### What is work?

* Camera
* Bluetooth
* Wifi
* 120Hz Display 
* Speaker / Mic
* NFC

### What is not work?

* Fingerprint
* VoLTE
* 60FPS Videos 