# Compatibility
Most Generic System Images work flawlessly, keep in mind the official kernel is 4.9 so GSIs that require newer kernels (like DerpFest) won't boot.

# Device components
- Wi-Fi: ✔ Working
- Bluetooth: ✔ Working (some reported problems when using the Android 10 Bluetooth firmware)
- GPS: ✔ Working
- Fingerprint: ⚠ Degraded (authentication works, some gestures don't work - see below for more information)
- FM Radio: ❓ Untested
- Stock camera: ✔ Available (slightly older version), check [Syoker's module](https://github.com/syoker/moto-experience).

## The fingerprint issue
Some device owners reported different issues with the phone while running a GSI. They depend on your fingerprint module manufacturer. You can check which one you have with apps like [Device Info HW](https://play.google.com/store/apps/details?id=ru.andr7e.deviceinfohw).

- **Goodix vendor:** The FPS module sends the volume down keycode whenever pressed (only when unlocked) and the system does so. "Swipe fingerprint for notifications" doesn't work at all.
- **FPC vendor:** Works as expected all of the time, but the FPS module doesn't send different keycodes for "swipe left" and "swipe right", so "Swipe fingerprint for notifications" works normally when in portrait but doesn't rotate the gesture. So, when in landscape, you still need to swipe top to bottom (from where the cameras are to where the charging port is) to pull down the shade.

_Notice: I am working in a custom kernel for astro which will, among other things, boost the GPU clock speed and try to fix those fingerprint issues. A download link will be provided if the custom kernel is proved stable._

## Stock applets
The following apps and Moto-exclusive features are available for GSIs thanks to [Syoker](https://github.com/syoker)'s work:
- Moto Gestures
- Moto Camera
- Moto Wallpapers
- Moto Weather Widget
- Moto Bootanimation

Link to the Magisk module [here](https://github.com/syoker/moto-experience).
_Notice: I am also working on a newer module to fix SELinux, update the Moto Camera, and more._

