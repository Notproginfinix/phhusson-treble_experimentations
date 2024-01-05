# Samsung Galaxy A22 4G

### Your warranty is now voided. Same with the Knox Warranty Bit. I am not responsible for bricked devices, dead SD cards, thermonuclear war, or you getting fired because the alarm app failed. Please do some research if you have any concerns about features included in the GSI you want to flash before flashing it! YOU are choosing to make these modifications, and if you point the finger at me for messing up your device, I will laugh at you. 

## Steps to install TWRP
* Flash [`TWRP`](https://drive.google.com/file/d/10bExm5EGMlP3x3S0H2BZ6yj-RrfFi8oC/view?usp=drive_link) in AP slot and [`vbmeta`](https://drive.google.com/file/d/1UrqhA9zxMOJ-sq-VQ9kmg-n_YcaFtoxa/view?usp=drive_link) in userdata slot in Odin3
* Boot into `TWRP`
* Wipe -> Format data >Type 'yes'
* Go to advanced -> terminal -> type `multidisabler`
* Reboot into `TWRP`
* Download [`Dynapatch.zip`](https://drive.google.com/file/d/1U-PTJXNXrdITt6aN1nYeS8kz2NHl7Nhi/view?usp=drive_link)
* Flash `Dynapatch.zip`

## Steps to install GSI
In `TWRP` 
* Wipe -> format data -> type 'yes' then swipe.
* Wipe -> Advanced wipe -> select Dalvik, data, cache and swipe.
* Install -> select IMG file as 'System Image' and swipe. (Note: Extract your GSI.img.xz to .img using WinRAR or 7zip on PC)
### And you're done!




## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera (front/main)       | Working ✅                                                  |
| Speaker / Mic             | Working ✅                                                  |
| Bluetooth                 | Working ⚠ (needs workarounds for full functionality)                |
| WiFi                      | Working ✅                                                  |
| SIM / Mobile Data / Voice | Working ✅                                                 |
| Dual SIM                  | Working ⚠ (needs workarounds for full functionality)    
| VoLTE                     | Not working ❌                                              |
| Fingerprint               | Working ✅                                                  |
| Face Unlock               | Not working           |
| Offline charging          | Working ✅                                                  |
| NFC                       | Probably working ❓ (untested but phone shows NFC in status bar)         |
| Hotspot / Usb tethering   | Working ✅                                                  |
| MTP                       | Working ✅                                                  |
| 90 HZ                     | Working ✅                                                  |
---

# Workarounds

## Non Root workarounds.

### Bluetooth workarounds (fixes no audio in bluetooth headset):
Open settings -> Phh treble settings -> Misc features -> Bluetooth workarounds -> select mediatek
Open settings -> Phh treble settings -> Misc features -> Use System wide bt hal

### No AOD:
Open settings -> Phh treble settings -> Misc features -> Force always on display (note: AOD for some reason never updates unless you get a notification, no workaround yet.)

## Rooted Workarounds
TBD

Thanks to this [Telegram community](https://t.me/Samsung_f22_Community) for all these guides!

### Test Log
Tested by [@devid7xw](https://github.com/devid7x) - SM-A225F, phh PixelOS 13

> Date tested - 2023-09-29


Tested by [@devid7xw](https://github.com/devid7x) - SM-A225F, phh Pixel Experience 13.0

> Date tested - 2023-07-08
