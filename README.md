# android_device_xiaomi_surya_twrp
For building TWRP for POCO X3

TWRP device tree for POCO X3

## Compile

First checkout minimal twrp with omnirom tree:

```
repo init -u git://github.com/minimal-manifest-twrp/platform_manifest_twrp_omni.git -b twrp-10.0
repo sync
```

Then add these projects to .repo/manifest.xml:

```xml
<project path="device/xiaomi/surya" name="windeqk/android_device_xiaomi_surya_twrp" remote="github" revision="android-10" />
```

Finally execute these:

```
. build/envsetup.sh
lunch omni_surya-eng
mka recoveryimage ALLOW_MISSING_DEPENDENCIES=true # Only if you use minimal twrp tree.
```

To test it:

```
fastboot boot out/target/product/surya/recovery.img
```

## Other Sources

Using precompiled stock kernel.
