# [Dali Smart Lamp T7] - [h2s]

Dali Smart Lamp (大力智能学习灯) T7 is an Android Lamp designed for monitoring kids doing homework. To unlock the bootloader, please flash the engineering OS before you proceed.

## Hardware Support

| Component                 |      Comment                                              |
|---------------------------|-----------------------------------------------------------|
| Camera                    | ?                                                         |
| Speaker / Mic             | ?                                                         |
| Bluetooth                 | ?                                                         |
| WiFi                      | ?                                                         |
| Lamp                      | ?                                                         |

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