# Samsung Galaxy A22 4G

## Steps to install TWRP
* Flash [`TWRP`](https://drive.google.com/file/d/10bExm5EGMlP3x3S0H2BZ6yj-RrfFi8oC/view?usp=drive_link) and [`vbmeta`](https://drive.google.com/file/d/1UrqhA9zxMOJ-sq-VQ9kmg-n_YcaFtoxa/view?usp=drive_link) in Odin
* Boot into `TWRP`
* Wipe -> Format data >Type 'yes'
* Go to advanced -> terminal -> type `multidisabler`
* Reboot into `TWRP`
* Download [`Dynapatch.zip`](https://drive.google.com/file/d/1U-PTJXNXrdITt6aN1nYeS8kz2NHl7Nhi/view?usp=drive_link)
* Flash `Dynapatch.zip`

## Steps to install GSI
In `TWRP` 
* Wipe > format data > type 'yes' then swipe.
* Wipe > Advanced wipe > select Dalvik, data, cache and swipe.
* Install > select img file as 'System Image' and swipe. (Note: Extract your GSI.img.xz to .img using WinRAR or 7zip on PC)
### And you're done!




## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Working                                                   |
| Speaker / Mic             | Working                                                   |
| Bluetooth                 | Working                                                   |
| WiFi                      | Working                                                   |
| SIM / Mobile Data / Voice | Working                                                   |
| Dual SIM                  | Working  (No LTE on SIM 2, everything else works on SIM 2)                                                 |    
| VoLTE                     | Not working                                               |
| Fingerprint               | Working*                                               |
| NFC                       | Untested                                                  |
| Hotspot / Usb tethering   | Working                                                   |
| MTP                       | Untested                                                  |
---

## Workarounds

### Bluetooth workarounds (fixes no audio in bluetooth headset):
Open settings -> Phh treble settings -> Misc features -> Bluetooth workarounds -> select mediatek
Open settings -> Phh treble settings -> Misc features -> Use System wide bt hal

### No AOD:
Open settings -> Phh treble settings -> Misc features -> Force always on display

Thanks to this [Telegram community](https://t.me/Samsung_f22_Community) for all these guides!

### Test Log
Tested by [@devid7xw](https://github.com/devid7x) - SM-A225F, phh Pixel Experience 13.0

> Date tested - 2023-07-08
