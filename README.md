<p align="center"><img src="user-guides/assets/mrdvs-logo-en.webp" alt="MRDVS Mobile Robot Vision Expert" width="280"></p>

<h1 align="center">MRDVS Application Algorithms</h1>

<p align="center"><strong>Application documentation, verified downloads, and release history for MRDVS 3D vision products.</strong></p>

## Find your application

Choose a product below to see its overview, guides, downloads and version history. **Already using our software?** Go to [Latest software](#latest-software); check your installed versions before updating.

<table>
<tr>
<td width="33%" align="center" valign="top">
<a href="aw3/README.md"><img src="user-guides/assets/button-aw3.svg" alt="AW3 Platform" width="220" height="44"></a><br><br>
Configure devices and manage supported vision applications.
</td>
<td width="33%" align="center" valign="top">
<a href="depalletizing/README.md"><img src="user-guides/assets/button-depalletizing.svg" alt="Depalletizing" width="220" height="44"></a><br><br>
Vision guidance for removing bags and cartons from a stack.
</td>
<td width="33%" align="center" valign="top">
<a href="pallet-docking/README.md"><img src="user-guides/assets/button-pallet-docking.svg" alt="Pallet Docking" width="220" height="44"></a><br><br>
Locate pallet entry faces and their orientation for autonomous forklift docking.
</td>
</tr>
<tr>
<td align="center" valign="top">
<a href="volume-measurement/README.md"><img src="user-guides/assets/button-volume-measurement.svg" alt="Volume Measurement" width="220" height="44"></a><br><br>
Measure object dimensions and volume at fixed inspection stations.
</td>
<td align="center" valign="top">
<a href="slot-monitoring/README.md"><img src="user-guides/assets/button-slot-monitoring.svg" alt="Slot Monitoring" width="220" height="44"></a><br><br>
Check storage-slot occupancy and cargo placement for warehouse operations.
</td>
<td align="center" valign="top">
<a href="obstacle-avoidance/README.md"><img src="user-guides/assets/button-obstacle-avoidance.svg" alt="Obstacle Avoidance" width="220" height="44"></a><br><br>
Detect 3D obstacles in configured zones for mobile robots and forklifts.
</td>
</tr>
</table>

## Application delivery model

AW3 provides a shared application interface. The diagram distinguishes current AW3 applications, planned migration and separate software.

<p align="center"><img src="user-guides/assets/aw3-application-model.svg" alt="AW3 supports Pallet Docking, Volume Measurement and Slot Monitoring. Depalletizing currently uses a standalone package, with AW3 migration planned. Obstacle Avoidance has a dedicated host application. LxCameraViewer and CameraSDK are shared tools." width="820"></p>

**Where to go next:** On the product page, read the guide for your deployment, check **Software history** and **Document history**, then choose the matching package. Download requirements are listed below.

## Latest software

| Product | Latest version | Release date | Download |
| --- | --- | --- | --- |
| [**AW3**](aw3/README.md) | [3.1.2](aw3/releases/README.md#aw3-312) | 2026-09-29 | [AW3 Installer](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/aw3-v3.1.2/AW3-V3.1.2_260929_win_x64.exe) · [User Manual](aw3/docs/aw3-application-algorithm-platform-user-manual-v0.1.pdf) |
| [**Depalletizing**](depalletizing/README.md) | [3.0.1](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/depalletizing/releases/README.md#legacy-standalone-301) · legacy standalone | 2026-07-03 | [Depalletizing Package (ZIP)](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/Depalletizing-Algorithm-V3.0.1/AW3-V3.0.1-20260624.zip) · [Deployment Guide](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/depalletizing/docs/deployment-guide.md) |
| [**Pallet&nbsp;Docking**](pallet-docking/README.md) | [SmartDocking 3.0.2](pallet-docking/releases/README.md#smartdocking-302) | 2026-09-29 | [SmartDocking Package](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/smartdocking-v3.0.2/SmartDocking-RKU20-V3.0.2_260929_linux_arm64.tar.gz) · [AW3 Installer](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/aw3-v3.1.2/AW3-V3.1.2_260929_win_x64.exe) · [User Manual](pallet-docking/docs/smartdocking-user-manual-v0.1.pdf) |
| [**Volume&nbsp;Measurement**](volume-measurement/README.md) | Delivered through [AW3 3.1.2](aw3/releases/README.md#aw3-312) | 2026-09-29 (AW3) | [AW3 Installer](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/aw3-v3.1.2/AW3-V3.1.2_260929_win_x64.exe) · [User Manual](volume-measurement/docs/torusmetric-user-manual-v0.1.pdf) |
| [**Slot&nbsp;Monitoring**](slot-monitoring/README.md) | [StockSync 3.1.1](slot-monitoring/releases/README.md#stocksync-311) | 2026-09-29 | [StockSync Package](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/stocksync-v3.1.1/AW3_camera_SDK_stocksync_full_update_rk3588_260924_3.1.1.tar.gz) · [AW3 Installer](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/aw3-v3.1.2/AW3-V3.1.2_260929_win_x64.exe) · [User Manual](slot-monitoring/docs/stocksync-user-manual-v0.1.pdf) |
| [**Obstacle&nbsp;Avoidance**](obstacle-avoidance/README.md) | [Workstation 1.0.19](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/obstacle-avoidance/releases/README.md#workstation-1019) | 2026-09-23 | [Obstacle Workstation Installer](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/aw3-obstacle-workstation-v1.0.19/AW3ObstacleWorkstation-Setup-1.0.19-x64.exe) · [User Manual](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/obstacle-avoidance/docs/obstacle-avoidance-user-manual-v0.1.pdf) |

Volume Measurement requires the AW3 installer only, with both frontend and backend installed. Slot Monitoring and Pallet Docking require the AW3 frontend plus their own algorithm `.tar.gz`; do not install the AW3 backend for these applications. The TorusMetric algorithm version is tracked separately from the AW3 installer version. Earlier [PalletPro packages](pallet-docking/README.md#legacy-palletpro) remain available for existing deployments. Obstacle Avoidance uses its dedicated host application.

## Required tools

| Tool | Use | Download | Guide |
| --- | --- | --- | --- |
| [**LxCameraViewer**](tools/lxcameraviewer/README.md) | Camera discovery, networking, parameter setup, and image or point-cloud verification. | [LxCameraViewer Installer](https://github.com/Lanxin-MRDVS/CameraSDK/releases/download/SDK-V2.4.60/MRDVS-2.4.60.260126-windows-installer.exe) | [User Guide](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/tools/lxcameraviewer/docs/user-guide.md) |
| [**CameraSDK**](https://github.com/Lanxin-MRDVS/CameraSDK) | Host-side camera APIs, SDK packages, and integration examples. | [SDK repository](https://github.com/Lanxin-MRDVS/CameraSDK#english) | [English documentation](https://github.com/Lanxin-MRDVS/CameraSDK#english) |

## Repository layout

```text
depalletizing/       Depalletizing guide and release history
pallet-docking/      Pallet Docking guide and release history
volume-measurement/  Volume Measurement guide and release history
slot-monitoring/     Slot Monitoring guide and release history
obstacle-avoidance/  Obstacle Avoidance guide and release history
aw3/                 AW3 platform releases
tools/               Shared camera and integration tools
user-guides/         Current documentation index and shared visuals
latest-downloads/    Current verified installation packages
```

Every application folder follows the same contract: `README.md` is the entry page, `docs/` stores the current guide, and `releases/README.md` is the single Release Notes file containing every version for that product.

Maintainers: [Release policy](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/user-guides/release-policy.md) · [Release-note template](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/user-guides/release-note-template.md) · [Repository structure](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/user-guides/repository-structure.md)

---

<sub>Hangzhou Lanxin Technology Co., Ltd. & MRDVS Co., Ltd. · All Rights Reserved. · Last updated: October 2026</sub>
