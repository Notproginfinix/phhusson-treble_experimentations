# Redmi 13C (gale/gust)
![Redmi 13C](https://fdn2.gsmarena.com/vv/bigpic/xiaomi-redmi-13c.jpg)

### Hardware support:
- Camera: working
- VoLTE: working (needs Phh Treble config)
- Bluetooth: working
- Wi-Fi: working
- SIM/Mobile Data: working
- Fingerprint: working
- NFC: not tested
- MTP: working
- Speaker/Mic: working

### Notes:
- If the screen goes dark during flashing in fastbootd, it's still in fastbootd. It's just turning the screen off to save power. You can wake the screen up by pressing the power button.

### Flashing instructions:

Step 1: Enter fastbootd: `adb reboot fastboot`

Step 2/1: Recreate product_a to free system space: `fastboot delete-logical-partition product_a`

Step 2/2: Recreate product_a to free system space: `fastboot create-logical-partition product_a 1000`

Step 3: Erase /system: `fastboot erase system`

Step 4: Flash GSI: `fastboot flash system PATH_TO_GSI.img`

Step 5: Erase userdata: `fastboot -w` # If this does not work, factory reset in recovery

Step 6: Flash stock boot (optional but recommended): `fastboot flash boot PATH_TO_BOOT.img`

Step 7: Disable dm-verity: `fastboot flash --disable-verity --disable-verification vbmeta PATH_TO_VBMETA.img`

Step 8: Reboot by running `fastboot reboot`

If the phone starts bootlooping, try holding the power up button till you get to recovery and doing a factory reset.