Installing a GSI on this device is really easy, all you need to do is unlocking the bootloader by just typing in the ADB terminal: `adb reboot bootloader` and then `fastboot flashing unlock` or `fastboot oem unlock`. 

**THIS WILL WIPE ALL YOUR DATA, BE AWARE AND CONSIDER DOING A BACKUP**. 

Next wait your device to turn on and redo all the setup. Unlock developer options again and grant ADB access, then from your ADB terminal send to your phone this command: 

adb reboot bootloader, after doing that copy and paste this long command, it will automatically flash your GSI and reboot after the installation: `fastboot reboot fastboot && fastboot erase userdata && fastboot erase metadata && fastboot delete-logical-partition product_b && fastboot delete-logical-partition product && fastboot delete-logical-partition product_a && fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img && fastboot flash vbmeta vbmeta.img && fastboot flash system system.img && fastboot flash recovery recovery.img && fastboot erase userdata && fastboot erase metadata && fastboot reboot`. 

Make sure that the GSI file name is `system.img`, the Vbmeta file is named `vbmeta.img` and that the recovery file (I suggest LineageOS Recovery) is named `recovery.img`

Happy modding.