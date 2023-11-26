## Preparation

This guide is only for Treble-enabled devices with **stock firmware**. For devices that were Treble-enabled via a custom firmware, please coordinate directly with its developer.

You should also have your stock firmware on hand and a method to extract system files from it, or have the stock firmware installed on your device. You can use [7-Zip ZS](https://github.com/mcmilk/7-Zip-zstd/releases/latest) to extract system files inside your firmware file.

This procedure assumes that you use an Ubuntu or Linux Mint machine. If you are on another Linux distro, you can use [Distrobox](https://github.com/89luca89/distrobox). If you are on Windows, you can use [WSL](https://learn.microsoft.com/en-us/windows/wsl/install).

### Setting up the necessary tools

Run the following commands:

```bash
sudo apt update
sudo apt upgrade
sudo apt install git xmlstarlet aapt apktool
```

## Locating the stock overlays

Find the following files on your firmware, either by extracting it from your stock firmware file or copying it from a device with stock firmware.

Grab the APKs from the following locations. If you can't see the exact file, just take a similarly-named APK on the directory, or look at other related directories. Whatever you find, grab it and set it aside for the procedure.

- `/system/product/overlay/framework-res__auto_generated_rro_product.apk`
- `/system/vendor/overlay/framework-res__auto_generated_rro_vendor.apk`

⚠️ Avoid taking values from the system partition. Those are extremely inaccurate generic information.

## Decompiling the stock overlays

To grab the values from the overlay APKs, `cd` into the directory where the overlay APK is stored, and run `apktool d nameOfApk.apk -o ./nameOfThePartitionTheApkCameFrom`.

Navigate to the `product` folder and get the `power_profile.xml` under `res/xml`. Do the same on the `vendor` folder. If there is no power profile on the product overlay or there is no difference between the power profile on the product and vendor overlays, then you don't need a power profile as it is on the vendor partition already.

Also, under `res/values`, take the files named `arrays.xml`, `bools.xml`, `dimens.xml`, `integers.xml`, and `strings.xml`. Do this to both `product` and `vendor`.

## Comparing the product and vendor overlays

The values on the product overlay is more accurate than the vendor partition. Also, flashing a GSI only overwrites the product partition and not the vendor partition. Therefore, the overlay you're creating only needs to include the overrides the product overlay has.

Compare the `arrays.xml`, `bools.xml`, `dimens.xml`, `integers.xml`, and `strings.xml` of the product and vendor partitions. Make a `config.xml` file and paste the following:

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    
</resources>
```

Inside the `<resources></resources>` part, put in all the values that product overlay has differences with the vendor overlay. You can use online text difference checkers for this part. **Read all the examples carefully for guidance.**

### Examples

![Image](https://i.imgur.com/Bnreq8d.png)

The vendor overlay is on the left, and the product overlay is on the right. The product overlay adds the following:

```xml
    <string-array name="config_biometric_sensors">
        <item>0:2:15</item>
        <item>1:8:4095</item>
    </string-array>
```

Therefore, this is now our `config.xml`:

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <string-array name="config_biometric_sensors">
        <item>0:2:15</item>
        <item>1:8:4095</item>
    </string-array>
</resources>
```

![Image](https://i.imgur.com/BQE2Urh.png)

The vendor overlay is on the left, and the product overlay is on the right. The product overlay does not have the following values even though the vendor overlay have those:

```xml
    <bool name="config_carrier_volte_available">true</bool>
    <bool name="config_carrier_volte_provisioned">true</bool>
    <bool name="config_carrier_volte_tty_supported">false</bool>
    <bool name="config_carrier_vt_available">true</bool>
    <bool name="config_device_volte_available">true</bool>
    <bool name="config_device_vt_available">true</bool>
    <bool name="config_device_wfc_ims_available">true</bool>
```

We are not gonna touch those values or add those to `config.xml` as it is not overridden by the product overlay.

Meanwhile, the product overlay has this value while the vendor does not have it:

```xml
   <bool name="config_supportAudioSourceUnprocessed">false</bool>
```

We are going to add it as it is not declared on the vendor overlay. This is now our `config.xml`:

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <string-array name="config_biometric_sensors">
        <item>0:2:15</item>
        <item>1:8:4095</item>
    </string-array>
    <bool name="config_supportAudioSourceUnprocessed">false</bool>
</resources>
```

Looking back, we have `power_profile.xml` and `config.xml`. This is what we are going to submit to the overlay repo.

## Creating your overlay

Fork [TrebleDroid/vendor_hardware_overlay](https://github.com/TrebleDroid/vendor_hardware_overlay) and clone the fork to your computer.

### Making `AndroidManifest.xml`

Run the `tests.sh` script under the `tests` folder an take note of the suggested priority number it outputs.

Under the folder of your phone's brand, make a folder for your model. Inside, make a file named `AndroidManifest.xml` and paste this:

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
        package="me.phh.treble.overlay.brandName.modelName"
        android:versionCode="1"
        android:versionName="1.0">
        <overlay android:targetPackage="android"
        	android:requiredSystemPropertyName="ro.vendor.build.fingerprint"
        	android:requiredSystemPropertyValue="+*brandName/modelName*"
		android:priority="yourSuggestedPriorityNumber"
		android:isStatic="true" />
</manifest>
```

Replace `yourSuggestedPriorityNumber` with the priority number you saw earlier. I got `553`.

Replace the `brandName` and `modelName` with information from running `getprop ro.vendor.build.fingerprint` on a terminal on your phone. For example, if I get `samsung/a03nnxx/a03:11/RP1A.200720.012/A035FXXU4CWI1:user/release-keys`, my `brandName` is `samsung` and my `modelName` is `a03`. This is now my example `AndroidManifest.xml`:

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
        package="me.phh.treble.overlay.samsung.a03"
        android:versionCode="1"
        android:versionName="1.0">
        <overlay android:targetPackage="android"
        	android:requiredSystemPropertyName="ro.vendor.build.fingerprint"
        	android:requiredSystemPropertyValue="+*samsung/a03*"
		android:priority="553"
		android:isStatic="true" />
</manifest>
```

### Making `Android.mk`

Make another file named `Android.mk` and paste this:

```makefile
LOCAL_PATH := $(call my-dir)
include $(CLEAR_VARS)
LOCAL_MODULE_TAGS := optional
LOCAL_PACKAGE_NAME := treble-overlay-brandName-modelName
LOCAL_MODULE_PATH := $(TARGET_OUT_PRODUCT)/overlay
LOCAL_IS_RUNTIME_RESOURCE_OVERLAY := true
LOCAL_PRIVATE_PLATFORM_APIS := true
include $(BUILD_PACKAGE)
```

Just replace `brandName` and `modelName` with the values you used earlier.

### Adding the overlay files

Make a `res` folder beside the two previous files, and inside it make `values` and `xml` folders. Inside the `xml` folder, place the `power_profile.xml` from earlier. Delete the `xml` folder if you don't need a power profile.

Place the `config.xml` file from earlier on the `values` folder.

### Adding your overlay to the build list

Open the `overlay.mk` file on the root of the repo you cloned and add the value of `LOCAL_PACKAGE_NAME` from your `Android.mk` to the list. Follow the alphabetical order, indentation, and don't forget the ` \` at the end of each items.

### Testing your overlay

Go to the `tests` folder again and run `tests.sh` script once more. Look for errors for your overlay. Delete values that causes errors and run the test script again. Do this until there are no more errors for your overlay.

### Building and retesting your overlay

Go to the `build` folder and run the `build.sh` script. When it is done building, look for the `treble-overlay-brandName-modelName.apk` for your device. Place it on `/system/vendor/overlay`, preferably by [making your own Magisk module](https://topjohnwu.github.io/Magisk/guides.html). See if your device runs fine with the module and if all issues are fixed. If not, modify the overlay further until it works.

## Submitting the overlay
If the overlay works properly, you can now make a pull request to get your overlay included on TrebleDroid sources. Simply go to your fork on GitHub click `Contribute` then `Open pull request`. Fill up the necessary info and confirm the action.

## Now what?

Look out on your device's groups or forums if there are any issues with GSIs built after the time your pull request was approved. It may be related to your overlay. Feel free to fix it and send an updated overlay.

## Help

If you need any help, do not hesitate to ask on [our Telegram group](https://t.me/phhtreble).