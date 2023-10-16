# Lenovo K12 Note (Guamp)

<img src="https://villman.com/product_photos/k12notesapphireblue_f30r6.gif"/>

# Device Specification

Basic   | Spec Sheet
-------:|:-------------------------
Display | 6.5-inch IPS LCD, 720 x 1600  pixels
Dimensions | 165.2 x 75.7 x 9.2 mm
CPU     | Octa-core (4x2.0 GHz Kryo 260 Gold & 4x1.8 GHz Kryo 260 Silver)
Chipset | Qualcomm SM6115 Snapdragon 662 (11 nm)
GPU     | Adreno 610
Memory  | 4GB
Internal Storage | 128GB
microSD | Up to 512 GB (uses shared SIM slot)
Battery | 5000 mAh
Triple Rear Camera  | 48 MP, f/1.7, (wide), 1/2.0", 0.8µm, PDAF
 | 2 MP, f/2.4, (macro)
 | 2 MP, f/2.4, (depth)
Front Camera | 8 MP (f/2.2, 1.12µm, HDR)
USB | USB Type-C 2.0
Shipped Android Version | 10.0 (Quince Tart)
Latest Android Version | 11.0 (Red Velvet Cake)

# Installation Process

* Unlock the `bootloader` using the documentations provided by motorola.
* Factory reset the device
* Power off the device and reboot to `fastboot` using key combinations `(Vol Down + Power)`
* Connect to PC with platform tools and drivers installed
* Reboot to fastbootd using fastboot utility
     ```
     $ fastboot reboot fastboot
     ```
* Erase the system partition
     ```
     $ fastboot erase system
     ```
* Note down the slot name. eg: `a for system_a` and `b for system_b`
* Delete the logical partition of product
     ```
     $ fastboot delete-logical-partition product_a [Replace the alphabet with the previously noted one]
     ```
* Download the gsi file and flash the system image
     ```
     $ fastboot flash system system.img [Replace with the file name]
     ```
* Wipe the userdata
     ```
     $ fastboot -w
     ```
* Reboot the device
     ```
     $ fastboot reboot
     ```

# Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Working                                              |
| Speaker / Mic             | Working                                              |
| Bluetooth                 | Working                                              |
| WiFi                      | Working                                              |
| SDCard                    | Working                                              |
| SIM / Mobile Data / Voice | Working                                              |
| VoLTE                     | Working [When IMS configured via app]                |
| Fingerprint               | Working                                              |
| NFC                       | This model does not have NFC                         |
| Fast Charging (15w)       | Working                                              |
| Offline Charging          | Working                                              |
| Boot                      | Working                                              |

Tested By: John Carandang

Model Tested: XT2083-4