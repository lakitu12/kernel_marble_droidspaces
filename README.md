# kernel_marble_droidspaces (branch: lineage-24.0)

Redmi Note 12 Turbo / POCO F5 (marble) kernel for DroidSpaces, built on the **LineageOS 24.0 kernel tree**.

- Base: `LineageOS/android_kernel_xiaomi_sm8450` @ `lineage-24.0` — Linux **5.10.269** (pinned revision)
- DroidSpaces: kABI-safe GKI patches (SYSVIPC + POSIX_MQUEUE, `below-kernel-6.12` set) + config fragment
- Root: **SukiSU Ultra** stable (**v4.2.1-40994**, pinned commit) + **KPM**
  - SUSFS is a SukiSU `builtin`-branch-only feature and is intentionally not part of this build
- LTO/CFI: `LTO_CLANG_THIN` + `CFI_CLANG=y` (thin LTO keeps CFI; stock LineageOS kernel uses LTO_CLANG_FULL)
- Kernel version string: `5.10.269-gki-droidspaces-lakitu`
- Every upstream (kernel / SukiSU / Droidspaces / AnyKernel3 / clang) is pinned by SHA in the workflow `env:`

## Build

GitHub Actions: push to this branch, or trigger "Run workflow" manually.
Artifacts: SukiSU-app-compatible AnyKernel3 zip + raw `Image` (per variant: `ksu` / `bypass`).

## Flash

- AnyKernel3 zip via a KernelSU / SukiSU manager or an AK3-compatible flasher (original boot ramdisk is preserved)
- A/B device — when flashing images manually, flash both slots (`boot_a` + `boot_b`)

## Verify (on device)

```sh
su -c droidspaces check
# Settings -> Requirements -> Check Requirements -> all green
```

## Sources

- Kernel: https://github.com/LineageOS/android_kernel_xiaomi_sm8450 (branch `lineage-24.0`)
- DroidSpaces: https://github.com/ravindu644/Droidspaces-OSS
- SukiSU Ultra: https://github.com/SukiSU-Ultra/SukiSU-Ultra
- AnyKernel3 template: https://github.com/Numbersf/AnyKernel3