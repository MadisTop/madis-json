# Madis JSON

[English](README.md) | [简体中文](README.zh-CN.md)

Madis JSON：跨平台大文件 JSON 查看与分析工具，支持按需树形浏览、全文搜索、多文件差异对比和属性观察。

官方网站：<https://madis.top>

## 下载

请从 [GitHub Releases](https://github.com/MadisTop/madis-json/releases) 或 [Gitee 发行版](https://gitee.com/Madis/madis-json/releases) 下载最新安装包。

测试版本会标记为 **Pre-release**。安装前请使用随版本提供的 `SHA256SUMS.txt` 校验下载文件。

## 主要功能

- 大型 JSON 文件按需解析；64 位平台不设 4 GiB 人为上限，实际受系统映射能力限制
- 树形视图支持虚拟滚动、懒加载和分页
- 支持 2～8 个 JSON 文件并排对比、差异筛选和联动浏览
- 观察窗支持嵌套属性浏览，以及图片和网页预览
- 20 MB 以内文件可使用文本视图
- 支持搜索对象属性名和叶子值
- 支持文件选择、拖放、文件关联和剪贴板粘贴打开
- 支持复制属性名、值、JSON 路径和完整节点
- 支持明亮与暗色主题
- 支持 Windows、macOS 和 Linux

## 平台安装包

| 平台 | 安装包 |
| --- | --- |
| Windows x64 | NSIS `.exe`、`.msi` |
| Linux x64 | `.AppImage`、`.deb`、`.rpm` |
| macOS Intel | `.dmg` |
| macOS Apple Silicon | `.dmg` |

## 版本支持策略

官方二进制会定期验证已签名的版本策略。最新版即使发布超过一年也持续可用；发布更新版本后，每个旧版本最多再使用一个自然月，同时保留自身发布日期满一年的绝对上限，两者以较早时间为准，到期或被撤销后必须更新。最近一次验证成功后最多可离线使用 14 天。旧安装包仍可能完成安装，但过期版本会在启动时阻止进入主功能。

## 安装与签名提示

- **Windows**：安装前在文件属性中查看数字签名并核对发布者。SmartScreen 可能提示风险；请结合下载来源、校验信息和系统提示判断，不要绕过保护安装来源不明的软件。
- **Linux**：如该版本附带 `Madis-JSON-Linux-Signing-Key.asc` 和 `Madis-JSON-Linux-Signing-Fingerprint.txt`，请先通过可信渠道核对完整指纹再导入公钥。RPM 可在导入公钥后用 `rpm --checksig <文件.rpm>` 验证；AppImage 可用 `<文件.AppImage> --appimage-signature` 查看嵌入签名信息。
- **macOS**：以 Gatekeeper 的实际校验结果为准，核对开发者身份和公证信息；系统无法验证时，先确认下载来源与校验信息，不要绕过保护安装来源不明的软件。
- 所有平台都应只从本仓库 Release 下载，并核对 `SHA256SUMS.txt`。Tauri Updater 的 `.sig` 是应用内更新验签文件，不等于 Windows、macOS 或 Linux 的系统代码签名。

## 数据与隐私

- 观察窗中可见的网络链接会自动发起访问，可能向目标站点披露 IP 地址等常规请求信息；处理敏感数据时请留意链接目标。
- 网页预览限制了脚本、表单、弹窗和同源权限；部分网站会拒绝嵌入，可能无法显示预览。

## 问题反馈

安装或使用过程中遇到问题，可以通过本仓库的 Issues 页面反馈。请勿在问题附件或截图中包含私密 JSON 数据。
