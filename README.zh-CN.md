# Madis JSON

[English](README.md) | [简体中文](README.zh-CN.md)

一款快速、跨平台的桌面 JSON 文件查看工具，专为处理大型 JSON 文件而设计。

官方网站：<https://madis.top>

## 下载

Windows 用户未来可优先从 Microsoft Store 安装；商店页面正在准备，在正式上线前请勿相信非官方商店链接。当前请从 [GitHub Releases](https://github.com/MadisTop/madis-json/releases) 或 [Gitee 发行版](https://gitee.com/Madis/madis-json/releases) 下载最新安装包。

测试版本会标记为 **Pre-release**。安装前请使用随版本提供的 `SHA256SUMS.txt` 校验下载文件。

## 主要功能

- 支持打开最大 2 GB 的 JSON 文件，并按需解析内容
- 树形视图支持虚拟滚动、懒加载和分页
- 20 MB 以内文件可使用文本视图
- 支持搜索对象属性名和叶子值
- 支持文件选择、拖放、文件关联和剪贴板粘贴打开
- 支持复制属性名、值、JSON 路径和完整节点
- 支持明亮与暗色主题
- 支持 Windows、macOS 和 Linux

## 平台安装包

| 平台 | 安装包 | 当前系统信任状态 |
| --- | --- | --- |
| Windows x64 | Microsoft Store MSIX（准备中）；NSIS `.exe`、`.msi` | Store 上线后优先使用商店版；直接下载版暂未 Authenticode 签名 |
| Linux x64 | `.AppImage`、`.deb`、`.rpm` | 稳定版的 AppImage/RPM 使用随版本公开的 OpenPGP 密钥原生签名 |
| macOS Intel | `.dmg` | 当前仅 ad-hoc 临时签名，暂未 Developer ID 签名和公证 |
| macOS Apple Silicon | `.dmg` | 当前仅 ad-hoc 临时签名，暂未 Developer ID 签名和公证 |

## 版本支持策略

官方二进制会定期验证已签名的版本策略。最新版即使发布超过一年也持续可用；发布更新版本后，每个旧版本仅可使用到其自身发布日期满一个自然年，到期或被撤销后必须更新。最近一次验证成功后最多可离线使用 14 天。旧安装包仍可能完成安装，但过期版本会在启动时阻止进入主功能。

## 安装与签名提示

- **Windows**：直接下载的 `.exe`/`.msi` 暂无 Authenticode 证书，SmartScreen 仍可能显示提示。Microsoft Store 版本上线后应优先使用商店安装和更新。
- **Linux**：稳定版会附带 `Madis-JSON-Linux-Signing-Key.asc` 和 `Madis-JSON-Linux-Signing-Fingerprint.txt`。导入前先核对完整指纹；RPM 可在导入公钥后用 `rpm --checksig <文件.rpm>` 验证。AppImage 可用 `<文件.AppImage> --appimage-signature` 检查嵌入签名信息。
- **macOS**：当前零预算阶段尚未加入 Apple Developer Program，DMG 未完成 Developer ID 签名与 Apple 公证，Gatekeeper 可能提示或阻止打开。
- 所有平台都应只从本仓库 Release 下载，并核对 `SHA256SUMS.txt`。Tauri Updater 的 `.sig` 是应用内更新验签文件，不等于 Windows、macOS 或 Linux 的系统代码签名。

## 问题反馈

安装或使用过程中遇到问题，可以通过本仓库的 Issues 页面反馈。请勿在问题附件或截图中包含私密 JSON 数据。
