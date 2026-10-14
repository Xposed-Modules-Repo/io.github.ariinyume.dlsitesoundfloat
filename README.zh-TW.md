<div align="center">

# DLsiteFloat

**DLsiteSound 懸浮窗 / 狀態欄字幕模組**

[简体中文](README.md) | **繁體中文** | [English](README.en.md)

[![GitHub release](https://img.shields.io/github/v/release/ariinyume/DLsiteFloat?style=flat-square)](https://github.com/ariinyume/DLsiteFloat/releases)
[![GitHub downloads](https://img.shields.io/github/downloads/ariinyume/DLsiteFloat/total?style=flat-square&color=blue)](https://github.com/ariinyume/DLsiteFloat/releases)
[![GitHub stars](https://img.shields.io/github/stars/ariinyume/DLsiteFloat?style=flat-square&color=yellow)](https://github.com/ariinyume/DLsiteFloat/stargazers)

</div>

---

## 功能特性

- **懸浮字幕窗**：在 DLsiteSound 播放頁掛一個與播放進度同步的字幕窗，可拖曳、可縮放。
- **狀態欄字幕**：把目前字幕行鏡像到系統狀態欄（在 SystemUI 程序內注入）。支援單程左移捲動、即時讓位時鐘與通知圖示區、流體雲動態避讓。
- **播放頁雙膠囊按鈕**：`狀態欄 開 / 關` 與 `懸浮窗 開 / 關`，隨頁面自動顯隱；無字幕時自動變灰或隱藏。
- **程序內懸浮窗**：視窗直接掛在 DLsiteSound 程序內，與各個 Hook 共享同一份字幕資料，無需跨程序 IPC、無需獨立 Service。
- **可單獨使用懸浮窗字幕**：未授權 `com.android.systemui` 作用域時，左側`狀態欄 開 / 關`按鈕不顯示。
- **自動擷取字幕**：攔截 DLsiteSound 的網路回應自動解析字幕 JSON，不依賴 URL 關鍵字。
- **字幕離線快取**：曾經線上播放過的音軌會自動快取字幕，之後斷網 / 飛航模式 / 不掛代理時照常顯示（只保存官方下發的字幕文字，按音軌存，不涉及音訊內容）。
- **換軌智慧處理**：切到無字幕音軌時先掛起並提示，等新音軌的字幕 JSON —— 無快取時等 5 秒、已有快取放寬到 15 秒，期間可提前收窗並在字幕到達後自動開回；**雲端優先、本機後備**，完全離線時直接讀本機快取。
- **液態玻璃**：懸浮窗面板與播放頁字幕按鈕可切換為液態玻璃質感 —— 背景模糊交給系統合成器做，玻璃材質由模組自繪。
- **視覺化設定頁**：模組自帶設定頁，可調主字幕 / 非活動行 / 排版 / 液態玻璃等參數，改完點「儲存設定」即生效。
- **多語言支援**：按**系統語言**取外掛顯示語言，支援**简体中文 / 繁體中文 / English**

## 適用範圍

| 項目 | 說明 |
| --- | --- |
| **目標 App** | DLsiteSound（`jp.co.eisys.dlsitesound`） |
| **框架** | LSPosed 2.2.0+（libxposed API 102） |
| **作用域** | 需勾選**兩個**：`jp.co.eisys.dlsitesound` 與 `com.android.systemui` |
| **Android 版本** | Android 7.0（minSdk 24）起，targetSdk 34 |
| **機型 / ROM** | 基於 ColorOS 16/17 測試製作，其它 ROM 理論上可用 |

## 使用說明

1. **下載模組**

   從主倉庫 [Releases](https://github.com/ariinyume/DLsiteFloat/releases/latest) 或本倉庫 [Releases](https://github.com/Xposed-Modules-Repo/io.github.ariinyume.dlsitesoundfloat/releases)頁面下載最新版本的 APK（通常情況下，兩者更新進度一致，若不一致以主倉庫為準）。

2. **安裝並啟用**

- 安裝 APK 到已 root 裝置
- 開啟 LSPosed 管理器，找到 **DLsiteFloat** 模組
- 勾選啟用，作用域**兩個都勾**：`jp.co.eisys.dlsitesound` + `com.android.systemui`
- **強制停止** DLsiteSound，並**重啟 SystemUI 或重啟手機**

3. **授予懸浮窗權限**

- 設定 → 應用程式 → DLsiteSound → 權限管理 → 特殊應用程式權限 → `懸浮窗`
- 設定 → 應用程式 → DLsiteFloat → 權限管理 → 特殊應用程式權限 → `懸浮窗`

4. **開始使用**

- 開啟 DLsiteSound 的**有字幕播放頁**，播放控制列上方出現兩個膠囊按鈕
- 左鍵開關**狀態欄字幕**，右鍵開關**懸浮窗**
- 懸浮窗面板任意處拖曳可移動，右下角把手拖曳可縮放

## 其他

 完整說明與機制細節見主倉庫：**<https://github.com/ariinyume/DLsiteFloat>**

 提交 Issue：**<https://github.com/ariinyume/DLsiteFloat/issues>**

 授權條款：GPL-3.0-or-later
