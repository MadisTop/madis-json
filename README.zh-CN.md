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

## 安装路径、数据与便携模式

- Windows NSIS 与 MSI 的新安装默认程序目录均为 `%LOCALAPPDATA%\Programs\Madis\JSON`；已有合法安装位置会保留。产品标识保持 `top.madis.json`。
- MSI 与 NSIS **不支持直接互转**，检测到另一类型的安装登记时会阻止覆盖；请先卸载旧类型（保留用户数据）再安装另一类型。
- 安装模式用户根：Windows `%LOCALAPPDATA%\Madis\JSON`；macOS `~/Library/Application Support/Madis/JSON`；Linux 为有效绝对 `$XDG_DATA_HOME/Madis/JSON`，否则 `~/.local/share/Madis/JSON`。
- 根下 `Data` 保存持久内容，`State` 保存状态，`Cache` 保存可再生内容，`WebView` 保存浏览器 profile 与 localStorage（Windows 实际 profile 路径为 `<root>/WebView/EBWebView`），`Logs` 仅在需要时创建。可信时间、策略序号与已签名版本策略保存在 `State/version-policy`，不可当缓存清理；粘贴 JSON 临时文件位于 `Cache/paste`，不使用系统临时目录。打开的原始 JSON 文件仍在用户选择的位置，不会自动复制到 Data。
- **Windows/Linux 便携模式**：传入 `--portable`，或在可执行文件旁创建严格内容为 `{"version":1}` 的 `portable.json`。marker 存在但无效会报错，不静默回退。`--portable` 不会自动写 marker；路径只相对于可执行文件，不取决于工作目录。程序目录必须可写。
- Linux AppImage 使用有效绝对 `APPIMAGE` 外层包路径作为程序锚点；marker 与 Data 都在外层包旁，不使用临时只读挂载或 cwd。`APPIMAGE` 存在但无效时明确报错。
- 便携根为 `<exe目录>/Data`，该目录本身就是持久内容根；`State`、`Cache`、`WebView`、`Logs` 都在其下，不产生 `Data/Data`。保留整个 Data（尤其 State/version-policy）才能保留便携状态。
- 便携模式仍检查签名版本策略、执行支持期限门禁并提示更新，但**不调用安装型 Updater、不自动更新便携程序**。请手动下载，关闭应用后替换程序文件并保留 Data；不要运行 NSIS/MSI 把便携版转换为安装版。
- **macOS 不支持便携模式**：`--portable` 或有效 marker 会明确拒绝启动。安装版 Data/State 使用上述新根，但 WKWebView profile/localStorage 由系统管理，不位于 WebView；不能通过自定义目录实现全便携，也不要写入签名后的 .app 内部。
- 普通卸载保留用户内容。NSIS 显式勾选删除数据时仅删除当前用户安装模式的 `%LOCALAPPDATA%\Madis\JSON`，不删除 Madis 父目录、旧 ID 目录或便携 Data；MSI 默认保留用户数据。手动清理便携版时仅删除该副本的 Data。
- 不在运行时自动迁移旧 ID 或旧用户目录，不改动原有用户数据。

## 数据与隐私

- 观察窗中可见的网络链接会自动发起访问，可能向目标站点披露 IP 地址等常规请求信息；处理敏感数据时请留意链接目标。
- 网页预览限制了脚本、表单、弹窗和同源权限；部分网站会拒绝嵌入，可能无法显示预览。

## 问题反馈

安装或使用过程中遇到问题，可以通过本仓库的 Issues 页面反馈。请勿在问题附件或截图中包含私密 JSON 数据。
