# GTM releases

Installable GTM packages and stable automatic-update metadata for Windows and QNAP.

## Current stable release

[GTM 1.0.1](https://github.com/juranart/gtm-releases/releases/tag/gtm-v1.0.1)

Component versions:

- Windows portable: **0.1.12-w1**
- QNAP Bootstrap: **1.2.22** / QPKG **4.2.22**
- Runtime: **1.0.1**
- Core: **3.18.46**
- WebUI: **4.7.74**
- Bridge: **5.14**, protocol **12**

## Windows

Use [GTM-Windows-portable-0.1.12-w1.zip](https://github.com/juranart/gtm-releases/releases/download/gtm-v1.0.1/GTM-Windows-portable-0.1.12-w1.zip).

Bootstrap checks the stable GitHub release every six hours. It downloads a complete portable bundle, verifies the repository, filename, size, SHA-256 and exact manifest, replaces the bundle atomically, performs a health check and rolls back if startup fails. The running Bootstrap version is shown in the launcher and WebUI.

## QNAP

In QNAP App Center open **Settings → App Repository → Add**:

- Name: `GTM GitHub`
- URL: `https://raw.githubusercontent.com/juranart/gtm-releases/main/repo.xml`

The catalog provides Bootstrap for QNAP x86_64 on QTS 5.0 or newer. Existing manually installed systems may need one manual QPKG update before App Center accepts this repository.

Bootstrap 1.2.22 checks the stable GitHub release for Runtime, Core, WebUI and Bridge. Modules are downloaded and verified independently, installed in dependency order, health checked and rolled back on failure. Bootstrap itself remains a QPKG and is updated through App Center or manual QPKG installation.

Updates of Runtime, Core or Bridge may restart managed MT5 instances. Runtime 1.0.1 and Bridge 5.14 are reused by immutable URL and digest from the earlier release; Core 3.18.46 and WebUI 4.7.74 are new in GTM 1.0.1.

## Integrity and transport

Use [SHA256SUMS.txt](https://github.com/juranart/gtm-releases/releases/download/gtm-v1.0.1/SHA256SUMS.txt) and [gtm-release-manifest-v1.json](https://github.com/juranart/gtm-releases/releases/download/gtm-v1.0.1/gtm-release-manifest-v1.json). Clients reject unexpected repositories, filenames, sizes, hashes, architectures, dependency ranges and Bridge protocol versions.

HTTP remains the authoritative Bridge command transport. This repository contains installers and release metadata. It does not contain trading accounts, passwords, NAS logs or MT5 working data.
