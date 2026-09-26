<div align="center">

# DLsiteFloat

**DLsiteSound 悬浮窗 / 状态栏字幕模块**

[![GitHub release](https://img.shields.io/github/v/release/ariinyume/DLSiteSoundFloatingSubtitle?style=flat-square)](https://github.com/ariinyume/DLSiteSoundFloatingSubtitle/releases)
[![GitHub downloads](https://img.shields.io/github/downloads/ariinyume/DLSiteSoundFloatingSubtitle/total?style=flat-square&color=blue)](https://github.com/ariinyume/DLSiteSoundFloatingSubtitle/releases)
[![GitHub stars](https://img.shields.io/github/stars/ariinyume/DLSiteSoundFloatingSubtitle?style=flat-square&color=yellow)](https://github.com/ariinyume/DLSiteSoundFloatingSubtitle/stargazers)

</div>

---

## 功能特性

- **悬浮字幕窗**：在 DLsiteSound 播放页挂一个与播放进度同步的字幕窗，可拖动、可缩放。
- **状态栏字幕**：把当前字幕行镜像到系统状态栏（在 SystemUI 进程内注入）。支持单程左移滚动、实时让位时钟与通知图标区、流体云动态避让。
- **播放页双胶囊按钮**：`状态栏 开 / 关` 与 `悬浮窗 开 / 关`，随页面自动显隐；无字幕时自动置灰或隐藏。
- **可单独使用悬浮窗字幕**：未授权 `com.android.systemui` 作用域时，左侧`状态栏 开 / 关`按钮不显示。
- **自动抓取字幕**：拦截 DLsiteSound 的网络响应自动解析字幕 JSON，不依赖 URL 关键词。
- **换轨智能处理**：切到无字幕音轨时挂起并提示，5 秒内字幕到达则自动恢复，否则自动关窗。
- **多语言支持**：按**系统语言**取插件显示语言，支持**简体中文 / 繁體中文 / English**

## 适配范围

| 项目 | 说明 |
| --- | --- |
| **目标 App** | DLsiteSound（`jp.co.eisys.dlsitesound`） |
| **框架** | LSPosed 2.2.0+（libxposed API 102） |
| **作用域** | 需勾选**两个**：`jp.co.eisys.dlsitesound` 与 `com.android.systemui` |
| **Android 版本** | Android 7.0（minSdk 24）起，targetSdk 34 |
| **机型 / ROM** | 基于 ColorOS 16 测试制作，其它 ROM 理论上可用 |

## 使用说明

1. **下载模块**

   从主仓库 [Releases](https://github.com/ariinyume/DLSiteSoundFloatingSubtitle/releases/latest) 或本仓库 [Releases](https://github.com/Xposed-Modules-Repo/io.github.ariinyume.dlsitesoundfloat/releases)页面下载最新版本的 APK（通常情况下，两者更新进度一致，若不一致以主仓库为准）。

2. **安装并启用**

- 安装 APK 到已 root 设备
- 打开 LSPosed 管理器，找到 **DLsiteFloat** 模块
- 勾选启用，作用域**两个都勾**：`jp.co.eisys.dlsitesound` + `com.android.systemui`
- **强制停止** DLsiteSound，并**重启 SystemUI 或重启手机**

3. **授予悬浮窗权限**

- 设置 → 应用 → DLsiteSound → 权限管理 → 特殊应用权限 → `悬浮窗`
- 设置 → 应用 → DLsiteFloat → 权限管理 → 特殊应用权限 → `悬浮窗`

4. **开始使用**

- 打开 DLsiteSound 的**有字幕播放页**，播放控制条上方出现两个胶囊按钮
- 左键开关**状态栏字幕**，右键开关**悬浮窗**
- 悬浮窗面板任意处拖动可移动，右下角手柄拖动可缩放

## 其他

 完整说明与机制细节见主仓库：**<https://github.com/ariinyume/DLSiteSoundFloatingSubtitle>**

 提交 Issue：**<https://github.com/ariinyume/DLSiteSoundFloatingSubtitle/issues>**

 许可证：GPL-3.0-only
