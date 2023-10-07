Unlock the bootloader 
**#Flashing Procedure**
fastboot reboot fastboot

fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img

fastboot --disable-verification flash vbmeta_system vbmeta_system.img

fastboot erase system

fastboot delete-logical-partition product_a

fastboot delete-logical-partition product_b

fastboot flash system system.img

fastboot -w

Tested AOSP 13.