# Madis JSON

[English](README.md) | [简体中文](README.zh-CN.md)

A fast, cross-platform desktop viewer designed for large JSON files.

Website: <https://madis.top>

## Download

Windows users will be able to install from Microsoft Store as the preferred option. The Store listing is still being prepared; do not trust unofficial Store links before it is announced. For now, download the latest installers from [GitHub Releases](https://github.com/MadisTop/madis-json/releases) or [Gitee Releases](https://gitee.com/Madis/madis-json/releases).

Test releases are marked as **Pre-release**. Verify downloaded files with the accompanying `SHA256SUMS.txt` before installation.

## Features

- Opens JSON files up to 4 GiB with on-demand parsing
- Tree view with virtual scrolling, lazy loading, and pagination
- Text view for files up to 20 MB
- Searches object keys and leaf values
- Opens files by file picker, drag and drop, file association, or clipboard paste
- Copies property names, values, JSON paths, and complete nodes
- Light and dark themes
- Available for Windows, macOS, and Linux

## Downloads by platform

| Platform | Packages | Current platform trust status |
| --- | --- | --- |
| Windows x64 | Microsoft Store MSIX (in preparation); NSIS `.exe`, `.msi` | Prefer the Store build once available; direct downloads are not yet Authenticode-signed |
| Linux x64 | `.AppImage`, `.deb`, `.rpm` | Stable AppImage and RPM builds use the OpenPGP key published with the release |
| macOS Intel | `.dmg` | Currently ad-hoc signed only; no Developer ID signing or notarization yet |
| macOS Apple Silicon | `.dmg` | Currently ad-hoc signed only; no Developer ID signing or notarization yet |

## Version support policy

Official binaries periodically verify a signed version policy. The latest supported version remains usable even after one year. After a newer version is released, each older version remains usable for at most one additional calendar month, while retaining an absolute limit of one calendar year from its own release date; the earlier deadline applies. Expired or revoked versions must be updated. A previously verified policy may be used offline for up to 14 days. An old installer may still complete installation, but an expired build is blocked from entering the main application at startup.

## Installation and signature notice

- **Windows:** Direct `.exe` and `.msi` downloads do not yet have an Authenticode certificate, so SmartScreen may still display a warning. Prefer Microsoft Store installation and updates after the listing becomes available.
- **Linux:** Stable releases include `Madis-JSON-Linux-Signing-Key.asc` and `Madis-JSON-Linux-Signing-Fingerprint.txt`. Check the full fingerprint before importing the key. After importing it, verify RPM packages with `rpm --checksig <file.rpm>`. Use `<file.AppImage> --appimage-signature` to inspect the embedded AppImage signature information.
- **macOS:** During the current zero-budget phase, the project has not joined the Apple Developer Program. DMG files do not yet have Developer ID signing or Apple notarization, so Gatekeeper may warn or block them.
- On every platform, download only from this repository's Releases and verify `SHA256SUMS.txt`. Tauri Updater `.sig` files protect in-app updates; they are not Windows, macOS, or Linux platform code-signing certificates.

## Feedback

Please report installation or usage problems through this repository's Issues page. Do not include private JSON data in issue attachments or screenshots.
