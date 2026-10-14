<div align="center">

# DLsiteFloat

**Floating window & status bar subtitles for DLsiteSound**

[简体中文](README.md) | [繁體中文](README.zh-TW.md) | **English**

[![GitHub release](https://img.shields.io/github/v/release/ariinyume/DLsiteFloat?style=flat-square)](https://github.com/ariinyume/DLsiteFloat/releases)
[![GitHub downloads](https://img.shields.io/github/downloads/ariinyume/DLsiteFloat/total?style=flat-square&color=blue)](https://github.com/ariinyume/DLsiteFloat/releases)
[![GitHub stars](https://img.shields.io/github/stars/ariinyume/DLsiteFloat?style=flat-square&color=yellow)](https://github.com/ariinyume/DLsiteFloat/stargazers)

</div>

---

## Features

- **Floating subtitle window**: pins a subtitle window synced with playback progress onto the DLsiteSound playback page; it can be dragged and resized.
- **Status bar subtitles**: mirrors the current subtitle line to the system status bar (injected inside the SystemUI process). Supports one-way leftward scrolling, real-time yielding to the clock and notification icon area, and dynamic Fluid Cloud avoidance.
- **Two pill buttons on the playback page**: `Status ON / OFF` and `Popup ON / OFF`, showing and hiding along with the page; greyed out or hidden automatically when there are no subtitles.
- **In-process floating window**: the window hangs directly inside the DLsiteSound process and shares the same subtitle data with every hook — no cross-process IPC and no separate Service.
- **The floating window can be used on its own**: when the `com.android.systemui` scope is not authorized, the `Status ON / OFF` button on the left is not shown.
- **Automatic subtitle capture**: intercepts DLsiteSound's network responses and parses the subtitle JSON — with no reliance on URL keywords.
- **Smart track switching**: when you switch to an audio track with no subtitles, handling is suspended first and a placeholder is shown while it waits for the new track's subtitle JSON — 5 s when there is no cache, relaxed to 15 s when cached cues exist; the window can be closed early and is reopened automatically once the subtitles arrive.
- **Liquid glass**: the floating window panel and the playback-page subtitle buttons can be switched to a liquid glass look — the background blur is done by the system compositor, while the glass material is drawn by the module itself.
- **Visual settings page**: the module ships its own settings page for tuning the main subtitle / inactive lines / typography / liquid glass and more; changes take effect as soon as you tap "Save settings".
- **Multilingual support**: the module's display language follows the **system language**, supporting **简体中文 / 繁體中文 / English**

## Compatibility

| Item | Description |
| --- | --- |
| **Target app** | DLsiteSound (`jp.co.eisys.dlsitesound`) |
| **Framework** | LSPosed 2.2.0+ (libxposed API 102) |
| **Scopes** | **Two** must be checked: `jp.co.eisys.dlsitesound` and `com.android.systemui` |
| **Android version** | Android 7.0 (minSdk 24) and up, targetSdk 34 |
| **Device / ROM** | Built and tested on ColorOS 16/17; other ROMs should work in theory |

## Getting started

1. **Download the module**

   Download the latest APK from the main repository's [Releases](https://github.com/ariinyume/DLsiteFloat/releases/latest) or from this repository's [Releases](https://github.com/Xposed-Modules-Repo/io.github.ariinyume.dlsitesoundfloat/releases) page (normally the two stay in sync; if they differ, the main repository wins).

2. **Install and enable**

- Install the APK on a rooted device
- Open LSPosed Manager and find the **DLsiteFloat** module
- Enable it and **check both** scopes: `jp.co.eisys.dlsitesound` + `com.android.systemui`
- **Force stop** DLsiteSound, then **restart SystemUI or reboot your phone**

3. **Grant overlay permission**

- Settings → Apps → DLsiteSound → Permissions → Special app access → `Display over other apps`
- Settings → Apps → DLsiteFloat → Permissions → Special app access → `Display over other apps`

4. **Start using it**

- Open a **playback page that has subtitles** in DLsiteSound; two pill buttons appear above the playback control bar
- The left button toggles **status bar subtitles**, the right one toggles the **floating window**
- Press anywhere on the floating window panel and drag to move it; drag the bottom-right handle to resize it

## More

 Full documentation and implementation details are in the main repository: **<https://github.com/ariinyume/DLsiteFloat>**

 File an issue: **<https://github.com/ariinyume/DLsiteFloat/issues>**

 License: GPL-3.0-or-later
