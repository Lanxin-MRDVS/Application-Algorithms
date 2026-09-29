# Obstacle Avoidance Release Notes

[Documentation Home](../../README.md) / [Obstacle Avoidance](../README.md) / Release Notes

This is the single release-note file for the dedicated Obstacle Workstation host application. Workstation versions do not identify the device-side obstacle algorithm or firmware.

| Version | Change baseline | Repository publication date | Package |
| --- | --- | --- | --- |
| [1.0.19](#workstation-1019) | 1.0.18 | 2026-09-23 | [Windows x64 installer](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/aw3-obstacle-workstation-v1.0.19/AW3ObstacleWorkstation-Setup-1.0.19-x64.exe) |

The supplied change record was compiled on **2026-09-22**. It supplements the existing package metadata; it does not create another 1.0.19 release or change its publication date.

<a id="workstation-1019"></a>

## Obstacle Workstation 1.0.19

### Changes from 1.0.18

- Fixed invalid I/O status display: a device value of `-1` is now displayed as invalid status `1000`.
- Renamed the Non-semantic clustering control to Obstacle bounding boxes to clarify its purpose.
- Improved Chinese, English, Japanese, and Vietnamese translations for error messages and dynamic UI elements, retaining SDK error codes for diagnostics.

### Continued support

- Automatic device discovery with device identifiers and SDK-version display.
- Obstacle-region, template, I/O-mode, and parameter management, including saving, activation, and readback.
- Improved operation ordering during template changes and device recovery, reducing interference from polling.
- Image and point-cloud viewing, administrator image export, and device image-save settings.
- Retains installation language, icons, and permission configuration; upgrades preserve the on-site permission configuration file.

### Upgrade notes

- Template and parameter capabilities depend on the device model and SDK.
- Check the active template, regions, and I/O status after updating.
- Upgrading the workstation does not automatically upgrade device firmware.

The following package, compatibility, installation, and rollback information is retained from the existing public release. Installation and hardware validation have not been repeated as part of this documentation update.

### Package and verification

| Item | Value |
| --- | --- |
| Product metadata | AW3 Obstacle Workstation |
| File version | 1.0.19.0 |
| Distribution | Windows x64 installer, as identified by the supplied package |
| Supported Windows versions and prerequisites | Not verified |
| Package | [AW3ObstacleWorkstation-Setup-1.0.19-x64.exe](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/aw3-obstacle-workstation-v1.0.19/AW3ObstacleWorkstation-Setup-1.0.19-x64.exe) |
| Size | 38,584,087 bytes |
| SHA-256 | `00b28a6aea63996df7b5d5ec6f20d8383a84500b7b7a657db3687bc91021342a` |
| Authenticode signature | Not signed |
| Validation performed | File version metadata and SHA-256 integrity checks; uploaded asset verified against the supplied file |
| Installation and device testing | Not performed as part of this publication |

[Download SHA256SUMS.txt](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/aw3-obstacle-workstation-v1.0.19/SHA256SUMS.txt)

The checksum verifies that the downloaded bytes match this published package; it is not a code-signing certificate or a safety certification. The installer is unsigned, so Windows may display an unknown-publisher warning. Follow your organization's software approval policy.

### Compatibility and documentation

The current solution documentation describes V1 zone-status output for S10, S10 Lite, and S11, and V2 zone status plus obstacle geometry and depth point clouds for S10 Pro. **The exact camera firmware, SDK dependencies, and compatibility matrix for installer 1.0.19 have not been verified.** S10 provides RGB but no physical I/O; S10 Lite provides physical I/O but no RGB.

- [User Manual V0.1 (PDF)](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/obstacle-avoidance/docs/obstacle-avoidance-user-manual-v0.1.pdf)
- [White Paper V0.1 (PDF)](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/obstacle-avoidance/docs/obstacle-avoidance-white-paper-v0.1.pdf)

These are the current solution documents, not a verified build-specific compatibility certification. No document version is changed by this software release.

### Installation, upgrade, and rollback

1. Review the user manual and confirm operating-system, camera, and firmware compatibility with the project owner before deployment.
2. Download the installer and verify its SHA-256 value against the published checksum.
3. For an existing installation, export and retain its configuration, calibration information, and known-working installer before making changes. Close the running workstation before installation.
4. Install through your approved process, then validate camera connectivity, calibration, templates, and safe/warning/alarm reporting in a controlled environment before operational use.

In-place upgrade compatibility, configuration migration, and automated rollback are **not verified**. This repository does not yet provide an earlier host installer. Retain the previous package and configuration independently; confirm a supported rollback procedure with the project owner before updating a deployed system.

### Known issues

No developer-provided known-issue list was supplied. This must not be interpreted as an absence of defects. The unsigned installer and unverified deployment compatibility described above remain relevant limitations.
