# Tested images
[Evolution X 7.9 v2023.05.04](https://github.com/ponces/treble_build_evo/releases/tag/v2023.05.04)

Working well, bugs/fixes mentioned below.

# Flashing
1. BACKUP ALL YOUR IMPORTANT DATA
2. flash [chopin_images_V14.0.22.12.5.DEV](http://bigota.d.miui.com/V14.0.22.12.5.DEV/chopin_images_V14.0.22.12.5.DEV_20221205.0000.00_13.0_cn_chinatelecom_dafa144a83.tgz) as base image. (You could use other image as base image, but you may come across different bugs)
3. `fastboot -w && fastboot reboot fastboot && fastboot delete-logical-partition product_a && fastboot flash system <path_to_image_above.img>`
4. reboot your phone and it's done

# Hardware Support post flashing

What's working:
- Wi-Fi
- Calls & Mobile Data (and 5G)
- Bluetooth connection
- 120Hz refresh rate
- Camera
- NFC
- Fingerprint

What's not fully functional(manual fixes attached below):
- Bluetooth headphones
- Backlight (screen brightness)
- Volume scale during phone calls

# Bug fixes
- Backlight sometimes glitches: Turn on all four options under `Phh Treble Settings - Misc - Backlight`
- Bluetooth headphones: Turn on `Phh Treble Settings - Misc - Other - Use System Wide BT HAL`
- VoLTE: Turn on all two options under `IMS features` and install IMS APK
- Handset speaker volume not adjustable: Refer to #1908 https://github.com/phhusson/treble_experimentations/issues/1908

If you found any other bugs, feel free to open an issue and @me there.