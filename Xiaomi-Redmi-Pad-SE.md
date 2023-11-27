## Installation process
Download the ROM and you must extract the .IMG file found inside, you can download any GSI ROM from this page:
https://github.com/phhusson/treble_experiments/wiki/Generic-System-Image-%28GSI%29-list

Copy the file into the platform-tools folder, if you do not have said folder you can download it from HERE: https://developer.android.com/studio/releases/platform-tools

You must also have the vbmeta.img file, you extract it from the Miui stock ROM, if you don't have it, you can extract it from the official ROM for fastboot from Xiaomi firmware. Once you have copied the ROM .img file and vbmeta.img to the platform-tools folder, simply run the following commands from the said folder in order and you can enjoy your AOSP ROM.

`fastboot --disable-verification flash vbmeta vbmeta.img`

`fastboot reboot fastboot`

`fastboot delete-logical-partition product_a`

`fastboot flash system nameROM.img`

`fastboot -w`

`fastboot erase userdata`

`fastboot reboot`

## Tested GSI ROMs
* Project Elixir 3.13
* ArrowOS 13.1
* EvolutionX 7.9.7

## What works and what doesn't work.
Apparently everything works, including the 90hz screen, if you find any Bug or error, do not hesitate to edit this page and add the error and I would greatly appreciate a possible solution.

# # # # I hope you have a great day ❤️