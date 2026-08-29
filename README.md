# kernel_marble_droidspaces

Redmi Note 12 Turbo / POCO F5 (marble) GKI 5.10.236 kernel for DroidSpaces

- Base: `common-android13-5.10` (5.10.236) GKI
- DroidSpaces: kABI-safe patches for GKI (SYSVIPC + POSIX_MQUEUE) + `gki_defconfig` fragment
- Root: **SukiSU Ultra** Latest + **KPM** enabled (`CONFIG_KPM=y`)
- Device: marble (SM7475 Snapdragon 7+ Gen 2) - HyperOS 3.0 Android 15 stock 5.10.236 compatible

## Build manually

See `.github/workflows/build.yml` - one-click GitHub Actions.

## DroidSpaces verification

```
su -c droidspaces check
# Settings -> Requirements -> Check Requirements -> all green
```

## Flash

AnyKernel3 zip via KernelSU Manager / `fastboot flash boot_ab boot.img`

a/b device: `boot_a` + `boot_b` + `vendor_boot_a/b` + `dtbo_a/b` keep in sync.

## Sources

- Kernel: https://android.googlesource.com/kernel/manifest -b common-android13-5.10
- DroidSpaces: https://github.com/ravindu644/Droidspaces-OSS
- SukiSU Ultra: https://github.com/SukiSU-Ultra/SukiSU-Ultra
