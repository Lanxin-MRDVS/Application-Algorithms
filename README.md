<p align="center"><img src=".gitbook/assets/mrdvs_logo.png" alt="MRDVS Logo" width="300"></p>

# MRDVS Application Algorithms

Deployment guides, software downloads, and release notes organized by MRDVS application algorithm.

<p align="center">
  <a href="PalletPro/README.md"><img src="assets/button-pallet-docking.svg" alt="Pallet Recognition &amp; Docking algorithm" width="248" height="20"></a>
  <a href="Obstacle-Avoidance/README.md"><img src="assets/button-obstacle-avoidance.svg" alt="Obstacle Avoidance algorithm" width="248" height="20"></a>
  <br>
  <a href="Depalletizing/README.md"><img src="assets/button-depalletizing.svg" alt="Depalletizing algorithm" width="248" height="20"></a>
  <a href="Storage-Location/README.md"><img src="assets/button-storage-location.svg" alt="Storage Location Detection algorithm" width="248" height="20"></a>
</p>

Choose an algorithm application below. Each entry brings together its deployment instructions, related software, and user guides.

## Find your application

| Algorithm application | Use case | Documentation |
| --- | --- | --- |
| **[Pallet Recognition & Docking](PalletPro/README.md)** | Pallet recognition and docking with Eagle-M cameras; configured using PalletPro. | [Overview & downloads](PalletPro/README.md) · [User guide](PalletPro/user-guide.md) |
| **[Obstacle Avoidance](Obstacle-Avoidance/README.md)** | Obstacle detection, detection zones, and communication outputs. | [Deployment guide](Obstacle-Avoidance/README.md) |
| **[Depalletizing](Depalletizing/README.md)** | Soft bag and carton unstacking with AW3 & PalletEye. | [Overview & downloads](Depalletizing/README.md) · [User guide](Depalletizing/user-guide.md) |
| **[Storage Location Detection](Storage-Location/README.md)** | Storage-location calibration and occupancy detection. | [User guide](Storage-Location/README.md) |

## Camera setup & tools

These shared tools support camera setup and integration across algorithm applications.

| Tool | Use it for | Resources |
| --- | --- | --- |
| **LxCameraViewer** | Camera connection, network setup, and image / point-cloud inspection. | [User guide](LxCameraViewer/README.md) |
| **Camera SDK & tools** | Camera SDK packages and related tools. | [CameraSDK repository](https://github.com/Lanxin-MRDVS/CameraSDK) |

New to camera setup? Start with the [LxCameraViewer guide](LxCameraViewer/README.md), then follow the deployment instructions for your application.

## Software downloads

| Software | Version | Download & details |
| --- | --- | --- |
| **PalletPro** | `1.4.8_260828` | [Windows installer & checksum](PalletPro/README.md#software-download) · [Release notes](PalletPro/release-notes.md) |
| **Depalletizing** | `V3.0.1` | [Release notes & packages](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/tag/Depalletizing-Algorithm-V3.0.1) |

Installers are distributed through **[GitHub Releases](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases)**. Each application folder contains its related documentation.

<details>
<summary>For maintainers: where to update content</summary>

| Location | Purpose |
| --- | --- |
| `PalletPro/` | Pallet recognition and docking overview, PalletPro user guide, and release notes. |
| `Obstacle-Avoidance/` | Obstacle avoidance deployment guide. |
| `Depalletizing/` | AW3/PalletEye overview and complete deployment guide. |
| `Storage-Location/` | Storage location detection user guide. |
| `LxCameraViewer/` | Camera setup and viewer user guide. |
| `README.md` | This user-facing documentation homepage. |
| `SUMMARY.md` | GitBook navigation, with algorithms and camera tools in separate groups. |

Keep the primary navigation organized by algorithm application. Put software names such as PalletPro, AW3, and PalletEye in the relevant descriptions or software sections; list shared camera tools separately. Keep related files inside the application folder. Use short names such as `user-guide.md` and `release-notes.md` when adding pages; use the folder's `README.md` as its entry page. Update this homepage, `SUMMARY.md`, and any release-page links when moving or renaming a document. Keep installer binaries in Releases and preserve existing download URLs.

</details>

---

<sub>Hangzhou Lanxin Technology Co., Ltd. & MRDVS Co., Ltd. · All Rights Reserved. · Last updated: August 2026</sub>
