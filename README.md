# S Vendor Kernel for MerlinX/Lancelot

An S vendor kernel builder thingy by a professional idiot™

## WARNING!!!

Do NOT flash the resulting kernel if you're running MIUI 12.5 (R vendor) firmware. It is compatible ONLY with MIUI 13.0 (S vendor) firmware.

## Usage

> After successful build, it will upload an AnyKernel3 zip in `Artifacts`, please flash to phone with a custom recovery and ADB Sideload.

First fork this repository to your account and edit config.env as follows, then click `Actions`, you will see `Build Kernel` option on the left side, click it and you will see `Run workflow` on the top of the big dialog box on the right side, click it, select the device you have, and it will start the build.

### Kernel Source

Kernel source has been hardcoded to point to [EmreDemirn's S vendor tree](https://github.com/EmreDemirn-Repos/android_kernel_xiaomi_mt6768-s/tree/lineage-20-upstream).

### Kernel file

Type of the image you need, usually the same as BOARD_KERNEL_IMAGE_NAME in your AOSP/Lineage device tree.

e.g. Image.gz-dtb

### Old Android support

Enable legacy functionality to allow Android 12-13 S vendor ROMs made before 2026 to boot.

**THIS WILL BREAK BOOTING ON NEWER S VENDOR ROMs FROM 2026 ONWARD!**

### Add APatch support

Will enable kernel configs required for APatch.

### Enable KernelSU

Will need to provide a KernelSU setup source link and repo tag/branch.

### Add Kprobes

If your kernel Kprobes is working properly, changing this to `true` will automatically add the configs to defconfig.

### KSU Hooks Patch

Required if Kprobes doesn't work.

### Add OverlayFS

Optional for certain KernelSU forks.

### Make boot image

If set to true, boot.img will be made, you need to provide `Source boot image`

### Source boot image

Provide a direct link to a boot image that will boot successfully, with the same kernel source code and the same device tree as your current system built from aosp, the image contains fstab, init, and DTB, without them it may bootloop or hard brick.

e.g. https://raw.githubusercontent.com/xiaoleGun/KernelSU_action/main/boot/boot-wayne-from-Miku-UI-latest.img

## Credits

- [AnyKernel3](https://github.com/osm0sis/AnyKernel3)
- [AOSP](https://android.googlesource.com)
- [KernelSU](https://github.com/tiann/KernelSU)
- [xiaoxindada](https://github.com/xiaoxindada)
- [xiaoleGun](https://github.com/xiaoleGun)
- [Jbub5](https://github.com/Jbub5)
- [MrShockWAVEog](https://github.com/MrShockWAVEog)
- [EmreDemirn](https://github.com/EmreDemirn)
