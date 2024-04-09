# Device

## Steps to install

See [this](https://xdaforums.com/t/samsung-galaxy-a03-rooting-and-gsi-installation-guide.4642322/) XDA forums thread.

## Hardware support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | Partially works, 1080p video capture is only 24 fps       |
| Speaker / Mic             | Works                                                     |
| Bluetooth                 | On bluetooth headphones, the sound is laggy and high delay|
| WiFi                      | Works                                                     |
| Tethering                 | Works, with full WPA3 and 5GHz support                    |
| SIM / Mobile Data / Voice | Partially works, incoming SMS need [this][1] module       |
| VoLTE/VoWiFi              | Does not work                                             |
| Face recognition          | Works (For Android 13, requires enable "Set BIOMETRIC_STRONG" in Settings -> Phh Treble Setting -> Misc features)            |
| Offline Charging          | Does not show percentage                                  |
---

Tested by:
- [@IverCoder](https://github.com/IverCoder), SM-A035F (XTC), A035FXXU4CWI1, on 2023-11-21
- [@2imkanna](https://github.com/2imkanna), SM-A035F (XXV), A035FXXU4CWI1, on 2024-01-10

[1]: https://github.com/IverCoder/a03nnxx-ril-rollback/releases/latest