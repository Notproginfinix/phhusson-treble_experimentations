# # Installation process
Download the ROM and you must extract the .IMG file found inside, copy the file into the platform-tools folder, if you do not have said folder you can download it from HERE.
You must also have the vbmeta.img file, you extract this from the Miui stock ROM, if you don't have it, you can download it from HERE.
Once you have copied the .img file of the ROM and the vbmeta.img into platform-tools, just run the following commands from said folder in order and you will be able to enjoy your AOSP ROM.

`fastboot --disable-verification flash vbmeta vbmeta.img`

`fastboot reboot fastboot`

`fastboot delete-logical-partition product_a`

`fastboot flash system nameROM.img`

`fastboot -w`

`fastboot erase userdata`

`fastboot reboot`