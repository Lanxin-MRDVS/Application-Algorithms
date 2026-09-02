# Release Index

[Documentation Home](README.md) / Release Index

This page is the single repository index for public AW3 platform packages, application updates, and supporting tools. Binary packages remain attached to GitHub Releases; the Markdown records in this repository provide durable, reviewable release history.

## Current downloads

| Channel | Version | Scope | Package | Release note | GitHub Release |
| --- | --- | --- | --- | --- | --- |
| AW3 platform | `3.0.1` | AW3 platform with the documented Depalletizing update | [AW3-V3.0.1-20260624.zip](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/Depalletizing-Algorithm-V3.0.1/AW3-V3.0.1-20260624.zip) | [Details](platform/aw3/releases/v3.0.1.md) | [Historical release page](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/tag/Depalletizing-Algorithm-V3.0.1) |
| Pallet Docking tool | `1.4.8_260828` | Standalone PalletPro Windows application | [PalletPro installer](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe) | [Details](applications/pallet-docking/releases/v1.4.8_260828.md) | [Release page](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/tag/PalletPro) |

## Release channels

| Channel | Version owner | Use it for | Required tag format |
| --- | --- | --- | --- |
| **AW3 platform** | AW3 | Major platform delivery, shared runtime changes, and coordinated application bundles. | `aw3-v<major>.<minor>.<patch>` |
| **Application package** | Individual application | Short-cycle fixes, algorithm tuning, and optional feature packages compatible with an AW3 range. | `<application>-v<major>.<minor>.<patch>` |
| **Tool** | Individual utility | Standalone utilities such as PalletPro when their lifecycle is independent from AW3. | `<tool>-v<version>` |

Existing tags `Depalletizing-Algorithm-V3.0.1` and `PalletPro` are retained because published download URLs must remain valid. New releases should use the formats above.

## Application histories

- [Depalletizing](applications/depalletizing/releases/README.md)
- [Pallet Docking](applications/pallet-docking/releases/README.md)
- [Volume Measurement](applications/volume-measurement/releases/README.md)
- [Slot Monitoring](applications/slot-monitoring/releases/README.md)
- [Obstacle Avoidance](applications/obstacle-avoidance/releases/README.md)

No public application package is listed until its package, version, compatibility information, and release note have been verified. See the [release policy](docs/release-policy.md) and use the [release-note template](docs/release-note-template.md) for every new version.
