## Installation process

Copy the file into the platform-tools folder, if you do not have said folder you can download it from HERE: https://developer.android.com/studio/releases/platform-tools

You must also have the vbmeta.img file, you extract it from the Miui stock ROM, if you don't have it, you can extract it from the official ROM for fastboot from Xiaomi firmware. Once you have copied the ROM .img file which is inside the .xz and vbmeta.img file into the platform-tools folder, simply run the following commands from the platform-tools folder in order and you can enjoy your ROM AOSP.

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

| Component | Comment |
| --- | --- |
| Camera | Works |
| Speaker/Mic | Works |
| Bluetooth | Works |
| Wi-Fi | Works |
| Display Refresh rate | 60Hz (90Hz in phh settings) |
| Screen Brightness | Works |
| Volume scale | Works |
| SafetyNet post root | More or less, sometimes it requires the Play Integrity module through Magisk or KSU to solve it in some ROMs. |
| Camera | Works |
| Speaker/Mic | Works (Not fully tested) |
| Offline Charging | Sometimes yes, restarting solves it |
| WideVine certification L1 | Work L1 |

# I hope you have a great day ❤️