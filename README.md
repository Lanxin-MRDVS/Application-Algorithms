<p align="center"><img src=".gitbook/assets/mrdvs_logo.png" alt="MRDVS Logo" width="300"></p>

# MRDVS Application Algorithms

Deployment guides, software downloads, and release notes for MRDVS vision applications.

<p align="center">
  <a href="PalletPro/README.md"><img src="https://img.shields.io/badge/PalletPro-1765EF?style=for-the-badge" alt="Open PalletPro documentation"></a>
  <a href="#find-your-application"><img src="https://img.shields.io/badge/User_Guides-334155?style=for-the-badge" alt="Browse all user guides"></a>
  <a href="#software-downloads"><img src="https://img.shields.io/badge/Downloads-087E8B?style=for-the-badge" alt="Find software downloads"></a>
</p>

Choose an application below. Each application page brings its related guides and resources together.

## Find your application

| Application | Use case | Documentation |
| --- | --- | --- |
| **[PalletPro](PalletPro/README.md)** | Pallet recognition and docking with Eagle-M cameras. | [Overview & downloads](PalletPro/README.md) · [User guide](PalletPro/user-guide.md) |
| **[Obstacle Avoidance](Obstacle-Avoidance/README.md)** | Obstacle detection, detection zones, and communication outputs. | [Deployment guide](Obstacle-Avoidance/README.md) |
| **[Depalletizing](Depalletizing/README.md)** | Soft bag and carton unstacking with AW3 & PalletEye. | [Overview & downloads](Depalletizing/README.md) · [User guide](Depalletizing/user-guide.md) |
| **[Storage Location Detection](Storage-Location/README.md)** | Storage-location setup, camera calibration, and occupancy results. | [User guide](Storage-Location/README.md) |
| **[LxCameraViewer](LxCameraViewer/README.md)** | Camera connection, network setup, and image / point-cloud inspection. | [User guide](LxCameraViewer/README.md) |

New to camera setup? Start with the [LxCameraViewer guide](LxCameraViewer/README.md), then follow the deployment instructions for your application.

## Software downloads

| Software | Version | Download & details |
| --- | --- | --- |
| **PalletPro** | `1.4.8_260828` | [Windows installer & checksum](PalletPro/README.md#software-download) · [Release notes](PalletPro/release-notes.md) |
| **Depalletizing** | `V3.0.1` | [Release notes & packages](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/tag/Depalletizing-Algorithm-V3.0.1) |
| **Camera SDK & tools** | See SDK repository | [CameraSDK](https://github.com/Lanxin-MRDVS/CameraSDK) |

Installers are distributed through **[GitHub Releases](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases)**. Each application folder contains its related documentation.

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
