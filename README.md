# Madis JSON

[English](README.md) | [简体中文](README.zh-CN.md)

A cross-platform viewer and analysis tool for large JSON files, with on-demand tree browsing, full-text search, multi-file comparison, and property watches.

Website: <https://madis.top>

## Download

Download the latest installers from [GitHub Releases](https://github.com/MadisTop/madis-json/releases) or [Gitee Releases](https://gitee.com/Madis/madis-json/releases).

Test releases are marked as **Pre-release**. Verify downloaded files with the accompanying `SHA256SUMS.txt` before installation.

## Features

- Parses large JSON files on demand; no artificial 4 GiB limit on 64-bit platforms, subject to system mapping capacity
- Tree view with virtual scrolling, lazy loading, and pagination
- Compares 2–8 JSON files side by side with difference filtering and synchronized browsing
- Watches nested properties with image and web previews
- Text view for files up to 20 MB
- Searches object keys and leaf values
- Opens files by file picker, drag and drop, file association, or clipboard paste
- Copies property names, values, JSON paths, and complete nodes
- Light and dark themes
- Available for Windows, macOS, and Linux

## Downloads by platform

| Platform | Packages |
| --- | --- |
| Windows x64 | NSIS `.exe`, `.msi` |
| Linux x64 | `.AppImage`, `.deb`, `.rpm` |
| macOS Intel | `.dmg` |
| macOS Apple Silicon | `.dmg` |

## Version support policy

Official binaries periodically verify a signed version policy. The latest supported version remains usable even after one year. After a newer version is released, each older version remains usable for at most one additional calendar month, while retaining an absolute limit of one calendar year from its own release date; the earlier deadline applies. Expired or revoked versions must be updated. A previously verified policy may be used offline for up to 14 days. An old installer may still complete installation, but an expired build is blocked from entering the main application at startup.

## Installation and signature notice

- **Windows:** Before installation, inspect the digital signature in file properties and verify the publisher. SmartScreen may display a warning; review the download source, checksum information, and system prompts instead of bypassing protection to install software from an unknown source.
- **Linux:** If the release includes `Madis-JSON-Linux-Signing-Key.asc` and `Madis-JSON-Linux-Signing-Fingerprint.txt`, verify the full fingerprint through a trusted channel before importing the key. After importing it, use `rpm --checksig <file.rpm>` to verify RPM packages. Use `<file.AppImage> --appimage-signature` to inspect embedded AppImage signature information.
- **macOS:** Follow Gatekeeper's actual verification result and check the developer identity and notarization information. If the system cannot verify the software, confirm the download source and checksum information instead of bypassing protection to install software from an unknown source.
- On every platform, download only from this repository's Releases and verify `SHA256SUMS.txt`. Tauri Updater `.sig` files protect in-app updates; they are not Windows, macOS, or Linux platform code-signing certificates.

## Installation paths, data, and portable mode

- New Windows NSIS and MSI installations both default to `%LOCALAPPDATA%\Programs\Madis\JSON`; valid existing installation locations are retained. The application identifier remains `top.madis.json`.
- **Direct MSI/NSIS switching is unsupported.** An existing registration of the other installer type blocks installation. Uninstall the previous type first, retaining user data, then install the other type.
- Installed user root: Windows `%LOCALAPPDATA%\Madis\JSON`; macOS `~/Library/Application Support/Madis/JSON`; Linux uses an absolute `$XDG_DATA_HOME/Madis/JSON`, falling back to `~/.local/share/Madis/JSON` when XDG_DATA_HOME is unset or invalid.
- Under that root, `Data` holds persistent content, `State` holds state, `Cache` holds regenerable content, `WebView` holds the browser profile and localStorage (on Windows the actual profile path is `<root>/WebView/EBWebView`), and `Logs` is created only when needed. Signed version policies, trusted time, and anti-rollback sequence state belong in `State/version-policy`, not disposable cache. Pasted JSON temporary files use `Cache/paste`, not the system temp directory. Original JSON files stay where you opened them; they are not automatically copied into Data.
- **Windows/Linux portable mode:** pass `--portable`, or place a `portable.json` file containing exactly `{"version":1}` beside the executable. An existing but invalid marker is an error, never a silent fallback. The flag does not create a marker. Paths depend on the executable location, never the working directory; the program directory must be writable.
- Linux AppImage uses the valid absolute outer `APPIMAGE` package path as its executable anchor. The marker and Data sit beside that package, never in its temporary read-only mount or cwd. A present but invalid APPIMAGE value is an error.
- The portable root is `<executable-directory>/Data`, which itself holds persistent content. `State`, `Cache`, `WebView`, and `Logs` are children of this root; there is no `Data/Data`. Preserve the entire Data directory, especially State/version-policy, when replacing program files.
- Portable mode still checks signed version policies, enforces support deadlines, and announces available updates, but **never invokes the installer Updater and does not automatically update portable files**. Download manually, close the app, replace program files, and retain Data. Do not run NSIS/MSI to turn a portable copy into an installed application.
- **macOS portable mode is unsupported:** the flag or a valid marker produces a clear startup error. Installed Data/State use the new root above, but WKWebView profile/localStorage remain system-managed, outside WebView. Custom profile directories cannot provide full portability; do not write inside a signed .app bundle.
- Normal uninstall retains user content. NSIS's explicit delete-data option removes only the current user's installed `%LOCALAPPDATA%\Madis\JSON` root, never the Madis parent, legacy ID directories, or portable Data. MSI retains user data by default. To remove portable data manually, delete only that copy's Data directory.
- No runtime migration from previous identifiers or user directories is performed; existing user data is not modified.

## Data and privacy

- Visible network links in the watch panel are accessed automatically and may disclose your IP address and other standard request information to the destination; review link targets when working with sensitive data.
- Web previews restrict scripts, forms, popups, and same-origin permissions. Some sites block embedding and may not display a preview.

## Feedback

Please report installation or usage problems through this repository's Issues page. Do not include private JSON data in issue attachments or screenshots.
