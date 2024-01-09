# [Dali Smart Lamp T7] - [h2s]

Dali Smart Lamp (大力智能学习灯) T7 is an Android Lamp designed for monitoring kids doing homework. 

## How to access to System Settings Menu and Bootloader Unlock

* Tap the gear button on right top corner, then choose "设备管理" (Device Management).
* Tap the title "设备管理" 5 times continuously until you see a ladybug.
* Tap the ladybug - SWITCH tab, turn on "打开ADB" (Open ADB) switch.
* Tap the BUTTON tab, swipe up until you find "系统设置面板" (System Settings Panel). Tap "打开系统设置" to open System Settings.
* Get to "关于平板" (About Tablet), and tap "版本号" (Build version) 8 times.
* Tap the return button on top left corner, and tap "系统" (System) - "高级" (Advanced) - "开发者选项" (Developer Options).
* You should be able to turn on "OEM 解锁" (OEM Unlocking) here.
* Connect the lamp to PC and execute following commands to perform bootloader unlock:

```
adb reboot bootloader
fastboot flashing unlock
```

## Hardware Support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | ?                                                         |
| Speaker / Mic             | ?                                                         |
| Bluetooth                 | ?                                                         |
| WiFi                      | ?                                                         |
| Lamp Control              | ?                                                         |

## Additional Notes

The lamp brightness and color temperature control is kernel level. Following commands are done under ADB Shell so "adb shell" is ignored.

To turn on lamp:
```echo '1 0' > /sys/devices/platform/desklamp/driver/led_info```

To turn off lamp:
```echo '0 0' > /sys/devices/platform/desklamp/driver/led_info```

To toggle color temperature and brightness:
```echo '0 '${pwmA}' '${pwmB} > /sys/devices/platform/desklamp/driver/pwm_info```

where pwmA (warm light LED) and pwmB (cold light LED) are values between 10 and 1000

## Tested By:

@HikariCalyx @ Dali Smart Lamp T7 @ 06/01/2024

Template created by @zguithues