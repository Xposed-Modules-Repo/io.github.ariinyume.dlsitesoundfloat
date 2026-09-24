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
- **自动抓取字幕**：拦截 DLsiteSound 的网络响应自动解析字幕 JSON，不依赖 URL 关键词。
- **换轨智能处理**：切到无字幕音轨时挂起并提示，3 秒内字幕到达则自动恢复，否则自动关窗。

## 适配范围

| 项目 | 说明 |
| --- | --- |
| **目标 App** | DLsiteSound（`jp.co.eisys.dlsitesound`） |
| **框架** | LSPosed 2.2.0+（libxposed API 102） |
| **作用域** | 需勾选**两个**：`jp.co.eisys.dlsitesound` 与 `com.android.systemui` |
| **Android 版本** | Android 7.0（minSdk 24）起，targetSdk 34 |
| **机型 / ROM** | 针对 ColorOS 16 测试适配，其它 ROM 理论上可用 |

## 使用说明

1. **下载模块**

   从 [Releases](https://github.com/ariinyume/DLSiteSoundFloatingSubtitle/releases/latest) 页面下载最新版本的 APK。

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

## 详细文档

完整说明、机制细节与排障手册见主仓库：

**<https://github.com/ariinyume/DLSiteSoundFloatingSubtitle>**

## 免责声明

1. 本项目主要用于个人技术研究 / 学习目的，作者**不鼓励不建议**将其用于商业用途。
2. 本项目只研究**客户端字幕显示行为**，不绕过任何 DRM，不修改、不提取受版权保护的音频 / 文本内容本体。
3. 本模块与 DLsiteSound（eisys 株式会社）及各手机厂商**无任何隶属或合作关系**。
4. 使用本模块需要 **Root 与 Xposed 框架**，可能带来系统不稳定、失去保修、安全风险等后果，**由此带来的任何风险由使用者自行承担**。
5. 适配依赖目标 App 的内部实现，App 更新可能导致模块失效；作者**不保证**模块长期可用。
6. 下载、使用本模块即视为同意上述条款。

## 许可证

本项目采用 **GNU General Public License v3.0**（GPL-3.0）。
