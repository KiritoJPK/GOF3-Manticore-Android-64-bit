<div align="center">

# Galaxy on Fire 3 Manticore — Offline Android 64-bit

**Galaxy on Fire 3 Manticore running offline on modern 64-bit Android devices.**

[![Discord](https://dcbadge.limes.pink/api/server/N4F4aMQ6XP?style=flat)](https://discord.com/invite/N4F4aMQ6XP)
[![X (Twitter)](https://img.shields.io/twitter/follow/KiritoJPK?style=flat&logo=x)](https://twitter.com/KiritoJPK)
[![Downloads](https://img.shields.io/github/downloads/KiritoJPK/GOF3-Manticore-Android-64-bits/total)](https://github.com/KiritoJPK/GOF3-Manticore-Android-64-bits/releases)
[![Release](https://img.shields.io/github/release/KiritoJPK/GOF3-Manticore-Android-64-bits)](https://github.com/KiritoJPK/GOF3-Manticore-Android-64-bits/releases/latest)

**[⬇ Download the latest release](https://github.com/KiritoJPK/GOF3-Manticore-Android-64-bits/releases/latest)**

If you liked the project and would like to help me keep it going with a donation, I would be very grateful. [![Ko-fi](https://img.shields.io/badge/Ko--fi-FF5E5B?logo=ko-fi&logoColor=white)](https://ko-fi.com/kiritojpk)

</div>

## About

Galaxy on Fire 3 Manticore for Android needed the game servers for almost everything, and those servers were shut down years ago. This project turns the Android version 2.1.3 into a full offline game, like the **Premium** edition on Nintendo Switch: no server, no account, no hired wingmen, no chests and no waiting timers.

The original Android game only exists as 32-bit code, and many recent phones can no longer run 32-bit apps. This version runs that same game on 64-bit devices through a bridge built on [Dynarmic](https://github.com/azahar-emu/dynarmic), which translates the game's ARM32 code to ARM64 while it runs.

## Features

### Offline play
- The whole campaign plays offline, with the progress saved on the device
- The Premium progression of the Switch version, without online-only systems
- The informant system is kept: you still look for information before each boss

### Shop
- Ships, weapons and skins from the old online events and offers can be bought in the in-game shop with **Mhaan-Tiq**
- Every shop item costs a fixed **100 Mhaan-Tiq** for now
- The "store not available" error screen is gone

### Rewards and upgrades
- Enemies drop **credits**, with no limit per mission, and the credits are saved with your progress
- Enemies have a 25% chance to drop **1 to 5 Mhaan-Tiq**
- Weapon upgrades cost **credits**, and the *Upgrade now* button shows the credit icon

### Performance
- Faster emulation: direct calls, read-only game code and faster floating point
- The game runs with the OpenGL ES renderer

### Logs
- Each session writes a log to `GOF3/logs` in the root of the device storage (the 10 newest are kept), which helps when reporting bugs

## Requirements

- A device with a **64-bit ARM** processor (arm64-v8a)
- **Android 8.0** or newer
- The game's OBB files (main and patch)

## Installation

1. Install the APK.
2. Copy the `main.*.obb` and `patch.*.obb` files to
   `Android/obb/com.dsfishlabs.gofmanticore/`
3. Start the game and allow the storage permission, which the game uses for the log folder.

> [!NOTE]
> After a clean install the game always starts a new game, even if an older install left a credentials file in the root of the storage.

## Building the bridge

The bridge builds on Windows with `build_arm64.bat`. It needs:

- Android SDK with **NDK 27.2.12479018** and **CMake 3.22.1**
- **Git** (CMake downloads the pinned Dynarmic source)

The result is `libgofm.so`. The performance options can be turned on or off in `src/bridge_features.h`.

## Reporting bugs

Found a bug? Open an [issue](https://github.com/KiritoJPK/GOF3-Manticore-Android-64-bits/issues/new) or tell us on [Discord](https://discord.com/invite/N4F4aMQ6XP). Please check the [open issues](https://github.com/KiritoJPK/GOF3-Manticore-Android-64-bits/issues) first, in case it was already reported.

To help us fix it, include:

- **Device** model and **Android version**
- **Game version** (the release you installed)
- **What happened** and **what you expected**
- **Where** it happened (system, mission or menu) and the **steps** to make it happen again
- Whether it happens **every time** or only sometimes
- A **screenshot or video**, if you can
- The newest **log file** from `GOF3/logs`

If the game crashes or freezes, also say what you were doing right before it.

## Screenshots

![Screenshot](https://github.com/user-attachments/assets/59cb66f9-915d-4559-8a77-d65660e2d33c)
![Screenshot](https://github.com/user-attachments/assets/a0d8a9be-186a-4005-836f-e9056eff1e48)
![Screenshot](https://github.com/user-attachments/assets/0e0ddf1f-369b-4602-9a8e-307f444e4cf7)


## Credits

- **[Dynarmic](https://github.com/azahar-emu/dynarmic)**, the ARM translator the bridge is built on.

---

<sub>This is a non-commercial fan project and is not affiliated with FISHLABS or Deep Silver. Galaxy on Fire 3 Manticore and its assets belong to their respective owners.</sub>
