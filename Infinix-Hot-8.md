# Infinix Hot 8 (x650C)

Summary of what works and doesn't

* **Android 9**

Boots fine and everything is working fine except for offline charging.

   **Tested GSI**

   AOSP phh - BOOTS

   Havoc 2.9 - DOESN'T BOOT

   RR Pie - BOOTS

   LOS 16 - BOOTS

   Pixel Experience 9 - BOOTS

   Descendant - DOESN'T BOOT

   Others i haven't tested

* **Android 10**

Boots fine and everything works except the following

   **Bugs:**

   1. Offline charging as usual
   2. Crackling sound when playing media or even ringtones
   3. Media codec issue resulting to unplayable videos on WhatsApp, Telegram, Video player, etc

   **Tested GSI** 

   AOSP Phh 10 - BOOTS

   Havoc 3.x.x - BOOTS

   Pixel Experience 10 - BOOTS

   LOS 17 - BOOTS

   Others i haven't tested


* **Android 11**

Boots fine and everything is working

   **Bugs**
   1. VoLTE works after installing IMS APK.

   **Tested GSI**

   ASOSP Phh 11 - Boots

   DOT OS 5.1 - Boots

   DOT OS 5.2 - Boots - (So far the most stable, bugfree and recent GSI tested on X650C)

   Others not tested

* **Android 12**

Boots fine and everything is working except the following

   **Bugs**
   1. Wifi Hotspot, USB Tethering and Bluetooth tethering not working.
   2. VoLTE and Mobile Data works after installing IMS APK.

   **Tested GSI**

   ASOP Phh 12 - Boots

   Others not tested
 

## **Steps to install**

* **1. Unlock Bootloader**

  `fastboot oem unlock` or `fastboot flashing unlock`

* **2. Flash TWRP 3.3.1**

 Download TWRP 3.3.1 from [here](https://androidfilehost.com/?fid=4349826312261627248) made by Jackson Makinda

 Follow instructions in README.txt for flashing instruction and disabling encryption to access internal storage in TWRP

* **3. Flash vbmeta with disable verity**

 You must disable verified boot for this device to boot custom firmware or else you'll be stuck in a boot loop

 You must do this with vbmeta because magisk preserves dm-verity for system-as-root devices so you cant use magisk to disable it

 You can download vbmeta from [here](http://www.mediafire.com/file/bphav495l85wr0q/vbmeta.img/file)

 Then flash the file through fastboot by;

 ``
 $ fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
 ``

* **4. Flash a arm32binder64 A/B (A64 A/B) image with the `fastboot` utility:**

   For example;

    ```
    $ fastboot flash system system-arm32binder64-ab-gapps-su.img
    ```

* **5. As an alternative you can flash via TWRP as "System Image" and format data.**

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | WORKS                                                     |
| Speaker / Mic             | WORKS on Pie (crackling sounds on Android 10)             |
| Bluetooth                 | WORKS                                                     |
| Bluetooth Tethering       | WORKS (Doesn't works on Android 12 on X650C)              |
| WiFi                      | WORKS                                                     |
| SIM / Mobile Data / Voice | WORKS (after installing IMS APK on X650C)                 |
| VoLTE                     | WORKS (after installing IMS APK  on X650C)                |
| Fingerprint               | WORKS                                                     |
| NFC                       | NOT PRESENT                                               |
| Offline Charging          | NOT WORKING                                               |
| Hotspot                   | WORKS (Doesn't works on Android 12 X650C)                 |
| USB tethering            | WORKS (Doesn't works on Android 12 X650C)                  |
| Other feature             | All sensors work; Proximity, compass, gyro, etc           |
---

Tested By: Racka98 - x650B(International), December 5 Security Patch Vendor - 23 January 2020 - 

Template created by @zguithues and @hackintosh5 😍🫶
