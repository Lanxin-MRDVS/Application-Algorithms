<p align="center"><img src="assets/mrdvs-logo-en.webp" alt="MRDVS Mobile Robot Vision Expert" width="360"></p>

<h1 align="center">MRDVS Application Algorithms</h1>

Deployment guides, software downloads, and release notes organized by MRDVS application algorithm.

<p align="center">
  <a href="Depalletizing/README.md"><img src="assets/button-depalletizing.svg" alt="Depalletizing" width="160" height="36"></a>
  <a href="PalletPro/README.md"><img src="assets/button-pallet-docking.svg" alt="Pallet Docking" width="160" height="36"></a>
  <a href="Volume-Measurement/README.md"><img src="assets/button-volume-measurement.svg" alt="Volume Measurement" width="160" height="36"></a>
  <a href="Storage-Location/README.md"><img src="assets/button-storage-location.svg" alt="Slot Monitoring" width="160" height="36"></a>
  <a href="Obstacle-Avoidance/README.md"><img src="assets/button-obstacle-avoidance.svg" alt="Obstacle Avoidance" width="160" height="36"></a>
</p>

Choose an algorithm application below. Each entry brings together its deployment instructions, related software, and user guides.

## Find your application

| Algorithm application | Use case | Documentation |
| --- | --- | --- |
| **[Depalletizing](Depalletizing/README.md)** | Soft bag and carton unstacking with AW3 & PalletEye. | [Overview & downloads](Depalletizing/README.md) · [User guide](Depalletizing/user-guide.md) |
| **[Pallet Docking](PalletPro/README.md)** | Pallet recognition and precise forklift docking with Eagle-M cameras; configured using PalletPro. | [Overview & downloads](PalletPro/README.md) · [User guide](PalletPro/user-guide.md) |
| **[Volume Measurement](Volume-Measurement/README.md)** | 3D measurement of packages, pallets, luggage, and other objects. | [Overview & resources](Volume-Measurement/README.md) |
| **[Slot Monitoring](Storage-Location/README.md)** | Storage-location status, placement, and occupancy monitoring. | [User guide](Storage-Location/README.md) |
| **[Obstacle Avoidance](Obstacle-Avoidance/README.md)** | Obstacle detection, detection zones, and communication outputs. | [Deployment guide](Obstacle-Avoidance/README.md) |

## Camera setup & tools

These shared tools support camera setup and integration across algorithm applications.

| Tool | Use it for | Resources |
| --- | --- | --- |
| **LxCameraViewer** | Camera connection, network setup, and image / point-cloud inspection. | [User guide](LxCameraViewer/README.md) · [Download for Windows](https://github.com/Lanxin-MRDVS/CameraSDK/releases/download/SDK-V2.4.60/MRDVS-2.4.60.260126-windows-installer.exe) |
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
| `Volume-Measurement/` | Volume measurement overview and related integration resources. |
| `Storage-Location/` | Slot monitoring user guide. |
| `LxCameraViewer/` | Camera setup and viewer user guide. |
| `README.md` | This user-facing documentation homepage. |
| `SUMMARY.md` | GitBook navigation, with algorithms and camera tools in separate groups. |

Keep the primary navigation organized by algorithm application. Put software names such as PalletPro, AW3, and PalletEye in the relevant descriptions or software sections; list shared camera tools separately. Keep related files inside the application folder. Use short names such as `user-guide.md` and `release-notes.md` when adding pages; use the folder's `README.md` as its entry page. Update this homepage, `SUMMARY.md`, and any release-page links when moving or renaming a document. Keep installer binaries in Releases and preserve existing download URLs.

</details>

---

<sub>Hangzhou Lanxin Technology Co., Ltd. & MRDVS Co., Ltd. · All Rights Reserved. · Last updated: August 2026</sub>
