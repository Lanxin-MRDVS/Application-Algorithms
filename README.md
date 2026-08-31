<p align="center"><img src=".gitbook/assets/mrdvs_logo.png" alt="MRDVS Logo" width="240"></p>

# MRDVS Application Algorithms

Deployment guides, software downloads, and release notes for MRDVS vision applications. Choose your application below to get started.

## Find your application

| Application | What you can do | Open documentation |
| --- | --- | --- |
| **PalletPro — Pallet Recognition & Docking** | Install PalletPro, configure Eagle-M cameras, teach pallet positions, and integrate docking results. | [Start here](PalletPro/README.md) · [User guide](PalletPro/user-guide.md) |
| **Obstacle Avoidance** | Configure obstacle detection, detection zones, extrinsic calibration, and communication outputs. | [Deployment guide](Obstacle-Avoidance/README.md) |
| **Depalletizing — AW3 & PalletEye** | Deploy soft bag and carton unstacking, configure recognition, and calibrate robot grasping. | [Start here](Depalletizing/README.md) · [User guide](Depalletizing/user-guide.md) |
| **Storage Location Detection** | Set up storage locations, calibrate cameras, and read occupancy detection results. | [User guide](Storage-Location/README.md) |
| **LxCameraViewer — Camera Setup** | Connect cameras, configure networks and parameters, and inspect images and point clouds. | [User guide](LxCameraViewer/README.md) |

## Software downloads

- **PalletPro `1.4.8_260828`:** [Windows installer and checksum](PalletPro/README.md#software-download) · [Release notes](PalletPro/release-notes.md)
- **Depalletizing V3.0.1:** [Release notes and download links](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/tag/Depalletizing-Algorithm-V3.0.1)
- **Camera SDK and tools:** [CameraSDK repository](https://github.com/Lanxin-MRDVS/CameraSDK)
- **All application packages:** [GitHub Releases](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases)

Installers are distributed through GitHub Releases. Each application folder contains its related documentation.

<details>
<summary>For maintainers: where to update content</summary>

| Location | Purpose |
| --- | --- |
| `PalletPro/` | Product overview, user guide, and release notes. |
| `Obstacle-Avoidance/` | Obstacle avoidance deployment guide. |
| `Depalletizing/` | AW3/PalletEye overview and complete deployment guide. |
| `Storage-Location/` | Storage location detection user guide. |
| `LxCameraViewer/` | Camera setup and viewer user guide. |
| `README.md` | This user-facing documentation homepage. |
| `SUMMARY.md` | GitBook navigation, using the same application groups. |

Keep related files inside the application folder. Use short names such as `user-guide.md` and `release-notes.md` when adding pages; use the folder's `README.md` as its entry page. Update this homepage, `SUMMARY.md`, and any release-page links when moving or renaming a document. Keep installer binaries in Releases and preserve existing download URLs.

</details>

---

<sub>Hangzhou Lanxin Technology Co., Ltd. & MRDVS Co., Ltd. · All Rights Reserved. · Last updated: August 2026</sub>
