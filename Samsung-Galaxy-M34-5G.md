## Hardware support

| Component                        |      Comment                                                                                                 |
|----------------------------------|--------------------------------------------------------------------------------------------------------------|
| Camera (Including Wide Angle and Macro)                           | Working                                                                                                      |
| Speaker / Mic                    | Working                                                                                                      |
| Bluetooth                        | Working 
| Bluetooth Headphones                       | Working (Check Fixes)                                                                                                     |
| WiFi                             | Working                                                                                                      |
| SIM / Mobile Data / Voice        | Working                                                                                               |
| SMS | Working (Check fixes)
| VoLTE                            | Not Working                                                                                                  |
| Fingerprint                      | Working                                                                                                      |
| NFC                              | Working                                                                                                      |
| Offline Charging                 | Working (Check Fixes)                                                                                                 |
| 5G                               | Untested                                                                                                  |
| 120Hz Refresh Rate               | Working                                                                                                      |
| AOD | Working (Check fixes)



## Fixes

| Bug                        |      Fix                                                                                                 |
|----------------------------------|--------------------------------------------------------------------------------------------------------------|
| No Wide Angle and Macro                          | PHH Settings->Misc->Enable access to all cameras. Then install Open Camera->Settings->Camera API->Original Camera API                                                                                                       
| Offline Charging Stuck at Charging Logo                 | Change your plat_sepolicy.cil (/system/etc/selinux/) with this: https://www.mediafire.com/file/o09pjnxouxtg985/plat_sepolicy.cil/file                                                                                               
| BT Headphones Does Not Work During Phone Calls               | PHH Settings->Misc->Use System Wide BT HAL and PHH Settings->Misc->Set eSCO transport unit size->16                                                                                                      
| AOD Does Not Work Normally | Flash this module from Magisk:https://www.mediafire.com/file/fdpaswkd7x77t8h/AODEnabler2.zip.zip/file Then use this command from termux or PC: adb shell settings put secure double_tap_to_wake 1 
