# [Blackview BV9500] - [s32v63c2k_jk/MT6763V/CT]
## Hardware support

| Component                 | Pie                       | Q                         |
|---------------------------|---------------------------|---------------------------|
| Camera                    | Working, Front Cam Dimmed | Not Working               |
| Speaker / Mic             | Working                   | Working                   |
| Bluetooth                 | Working                   | Working                   |
| WiFi                      | Working                   | Working                   |
| SIM / Mobile Data / Voice | Working, Tested SIM1 Only | Partially, No SMS / Calls |
| Offline Charging          |                           |                           |
| Other feature             |                           |                           |
---

## Additional Information
This device is A-only with VNDK version 27.0, choose arm64-aonly when downloading an image.

You can get TWRP from [4pda](https://4pda.ru/forum/index.php?showtopic=908095&st=440#entry76833222). Install process used was TWRP - install image then wipe data/cache/dalvik.

## Test Results
  *  AOSP9v119, AOSP9v120  Boots ([With long boot workaround](https://github.com/phhusson/treble_experimentations/issues/576#issuecomment-504475775), without it either crashes or takes forever to boot)
  *  AOSP10v202  Boots ([With long boot workaround](https://github.com/phhusson/treble_experimentations/issues/576#issuecomment-504475775), without it either crashes or takes forever to boot. Must not have Magisk)
 ***
 ## Tested By:
* Joann Mõndresku
* Template created by @zguithues