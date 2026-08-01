# OrangeFox Recovery Builder — Moto G57 Power (mumba)

Build OrangeFox Recovery for Motorola Moto G57 Power via GitHub Actions.

## Device Info

| Property | Value |
|---|---|
| Codename | mumba |
| Model | moto g57 power |
| Android | 16 |
| Build | W1WAAS36.48-12-16-3 |
| Security Patch | 2026-03-01 |
| SoC | SM6435 (Snapdragon 6s Gen 4) |
| Platform | parrot |
| Architecture | arm64 (pure 64-bit) |
| Partition | A/B (VAB) |

## Build via GitHub Actions

1. Fork or push to GitHub
2. Go to **Actions** tab
3. Select **Build OrangeFox Recovery - Mumba**
4. Click **Run workflow**
5. Fill params:
   - `KERNEL_SOURCE` — default: Motorola official kernel
   - `KERNEL_BRANCH` — default: `MMI-W1WAAS36.48-12-16-3`
   - `ORANGEFOX_BRANCH` — default: `fox_12.1`
   - `INCLUDE_KSU` — patch KernelSU Next into kernel (default: true)
   - `KSU_VERSION` — KernelSU Next version tag (default: main)
6. Download artifact from Actions run

## Flash Instructions

```bash
fastboot flash recovery OrangeFox-mumba-*.img
fastboot reboot recovery
```

Or via `adb sideload` from stock recovery:
```bash
adb sideload OrangeFox-mumba-*.zip
```

## KernelSU Next

Workflow patches [KernelSU Next](https://github.com/rifsxd/KernelSU-Next) into kernel source before build.
Current version on device: `3.2.0`

## Maintainer

- **ndeso17** — khilmyfirdausr171102@gmail.com
- Device: Motorola Moto G57 Power (mumba)

## Credits

- [MotorolaMobilityLLC/kernel-msm](https://github.com/MotorolaMobilityLLC/kernel-msm) — official kernel source
- [OrangeFox Recovery Project](https://orangefox.download)
- [KernelSU Next](https://github.com/rifsxd/KernelSU-Next)
