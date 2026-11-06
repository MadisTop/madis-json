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

## Data and privacy

- Visible network links in the watch panel are accessed automatically and may disclose your IP address and other standard request information to the destination; review link targets when working with sensitive data.
- Web previews restrict scripts, forms, popups, and same-origin permissions. Some sites block embedding and may not display a preview.

## Feedback

Please report installation or usage problems through this repository's Issues page. Do not include private JSON data in issue attachments or screenshots.
