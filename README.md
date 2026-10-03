# GTM releases

Installable GTM packages and stable automatic-update metadata for Windows and QNAP.

## Current stable release

[GTM automatic updates — 2026-10-02](https://github.com/juranart/gtm-releases/releases/tag/gtm-2026.10.02-auto-updates)

Component versions:

- Windows Bootstrap: **0.1.10-w1**
- QNAP Bootstrap: **1.2.20** / QPKG **4.2.20**
- Runtime: **1.0.1**
- Core: **3.18.43**
- WebUI: **4.7.69**
- Bridge: **5.14**, protocol **12**

## Windows

Install [GTM-Setup-0.1.10-w1.exe](https://github.com/juranart/gtm-releases/releases/download/gtm-2026.10.02-auto-updates/GTM-Setup-0.1.10-w1.exe), or use [GTM-Windows-portable-0.1.10-w1.zip](https://github.com/juranart/gtm-releases/releases/download/gtm-2026.10.02-auto-updates/GTM-Windows-portable-0.1.10-w1.zip).

Bootstrap checks the stable GitHub release every six hours. It downloads a complete portable bundle, verifies the repository, filename, size, SHA-256 and exact manifest, replaces the bundle atomically, performs a health check and rolls back if startup fails. The running Bootstrap version is shown in the launcher and WebUI.

## QNAP

In QNAP App Center open **Settings → App Repository → Add**:

- Name: `GTM GitHub`
- URL: `https://raw.githubusercontent.com/juranart/gtm-releases/main/repo.xml`

The catalog provides Bootstrap for QNAP x86_64 on QTS 5.0 or newer. Existing manually installed systems may need one manual QPKG update before App Center accepts this repository.

Bootstrap 1.2.20 checks the stable GitHub release for Runtime, Core, WebUI and Bridge. Modules are downloaded and verified independently, installed in dependency order, health checked and rolled back on failure. Bootstrap itself remains a QPKG and is updated through App Center or manual QPKG installation.

Updates of Runtime, Core or Bridge may restart managed MT5 instances. Runtime and Bridge are included so the release is also a complete installable set for a new system.

## Integrity and transport

Use [SHA256SUMS.txt](https://github.com/juranart/gtm-releases/releases/download/gtm-2026.10.02-auto-updates/SHA256SUMS.txt) and the platform manifests in the release. Clients reject unexpected repositories, filenames, sizes, hashes, architectures, dependency ranges and Bridge protocol versions.

Persistent localhost TCP/WebSocket is used for Bridge SHADOW telemetry. HTTP remains the only authoritative command path, and the full broker snapshot cadence is unchanged.

This repository contains installers and release metadata. It does not contain trading accounts, passwords, NAS logs or MT5 working data.
