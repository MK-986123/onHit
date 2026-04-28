# onHit

<div align="center">

<img src="https://raw.githubusercontent.com/0penPublic/onHit/refs/heads/main/onhit-logo.svg" alt="icon" width="150" />

![Release Download](https://img.shields.io/github/downloads/Xposed-Modules-Repo/mba.vm.onhit/total?style=flat-square)
![Release Download](https://img.shields.io/github/downloads/0penPublic/onHit/total?style=flat-square)
[![Release Version](https://img.shields.io/github/v/release/0penPublic/onHit?style=flat-square)](https://github.com/0penPublic/onHit/releases/latest)
[![GitHub Star](https://img.shields.io/github/stars/0penPublic/onHit?style=flat-square)](https://github.com/0penPublic/onHit/stargazers)
[![GitHub Star](https://img.shields.io/github/stars/Xposed-Modules-Repo/mba.vm.onhit?style=flat-square)](https://github.com/Xposed-Modules-Repo/mba.vm.onhit/stargazers)
[![GitHub Fork](https://img.shields.io/github/forks/0penPublic/onHit?style=flat-square)](https://github.com/0penPublic/onHit/network/members)
![GitHub Repo size](https://img.shields.io/github/repo-size/0penPublic/onHit?style=flat-square&color=3cb371)
[![GitHub license](https://img.shields.io/github/license/0penPublic/onHit?style=flat-square)](LICENSE)
[![GitHub Repo Languages](https://img.shields.io/github/languages/top/0penPublic/onHit?style=flat-square)](https://github.com/0penPublic/onHit/search?l=kotlin)
[![Telegram](https://img.shields.io/badge/Telegram-on_hit-blue.svg?style=flat-square&color=12b7f5)](https://t.me/on_hit)

</div>

## What is onHit?

onHit is an **Xposed / LSPosed module** that simulates **NFC tag touch events at the system level**, allowing Android to parse **NDEF data** and dispatch NFC intents as if a real NFC tag were presented.

The app also includes a lightweight file manager that can:

- Read and save **NDEF data (raw bytes)** from physical NFC tags
- Write previously saved **NDEF files** back to physical NFC tags

All physical tag read and write operations use **public Android NFC APIs** and can work without Xposed. Xposed is only required for **tagless NDEF replay**, where the module injects a simulated NFC tag event into the system NFC service.

## Requirements

- A **rooted Android device**
- A working **LSPosed**, **Dreamland**, or similar Xposed-compatible environment
- A ROM whose NFC service still exposes hookable internals
- NFC hardware enabled on the device

## How to Use

1. Install the onHit application.
2. Enable the module in your Xposed environment.
3. Scope the module to the system NFC service:
   - **AOSP / most ROMs:** `com.android.nfc`
   - **Samsung One UI:** `com.samsung.android.nfc`
4. Open onHit and choose a storage folder for NDEF files.
5. Import NDEF data from a physical tag or from a local file.
6. Tap an NDEF file to replay it through the system NFC dispatch flow.

## Samsung Galaxy S23 Ultra / Android 16 / One UI 8

This repository now declares and handles both known NFC service package names used by supported targets:

- `com.android.nfc`
- `com.samsung.android.nfc`

For the best chance of working correctly on a Samsung Galaxy S23 Ultra running **Android 16 / One UI 8**, the device still needs all of the following:

- Root access that survives the current firmware build
- A current LSPosed-compatible stack that can still inject into Samsung system apps
- The module scoped to Samsung's NFC service package
- A Samsung firmware build where the NFC service still exposes the expected internal classes and methods

Known constraints:

- Samsung ships a vendor-customized NFC stack and Knox protections, so compatibility can change after OTA updates
- Samsung Wallet / payment flows and other integrity-protected features are outside the scope of this module
- If Samsung renames or hardens its NFC internals in a future build, additional hook updates may be required

## Limitations

- Behavior depends heavily on the Android version and vendor NFC implementation
- Some OEM frameworks may change or restrict NFC internals
- This project is for research, learning, and testing workflows, not production deployments
- Cross-device and cross-ROM compatibility is not guaranteed

## Acknowledgments

Special thanks to these projects:

- [LSPosed](https://github.com/LSPosed/LSPosed)
- [EzXHelper](https://github.com/KyuubiRan/EzXHelper)
- [AndroidX](https://developer.android.com/jetpack/androidx)

## Legal & Ethical Notice

This project is intended for **research, learning, and testing purposes only**.

Do **not** use it to:

- Bypass security mechanisms without authorization
- Attack or impersonate real-world NFC systems
- Violate laws, terms of service, or privacy policies

You are solely responsible for how you use this software.

## License

This project is licensed under the **GNU General Public License v2.0 (GPLv2)**.

You may use, modify, and redistribute this software under the terms of GPLv2. Any derivative work must also be distributed under the same license.

See `LICENSE` for the full license text.

## Star History

<a href="https://www.star-history.com/#0penPublic/onHit&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=0penPublic/onHit&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=0penPublic/onHit&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=0penPublic/onHit&type=date&legend=top-left" />
  </picture>
</a>
