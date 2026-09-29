# Pallet Docking

[Documentation Home](../README.md) / Pallet Docking

SmartDocking provides pallet recognition and forklift docking. AW3 provides the frontend for configuration and monitoring; SmartDocking is delivered as a separate algorithm package. The earlier PalletPro workflow remains available for existing deployments.

| Status | Value |
| --- | --- |
| Frontend | AW3; install the frontend only |
| Algorithm package | SmartDocking `.tar.gz`; not yet published |
| AW3 backend | Do not install for this application |
| Latest recorded algorithm | [SmartDocking `3.0.1`](releases/README.md#smartdocking-301); notes available |
| Legacy host application | PalletPro `1.4.8_260828`; retained below |

## Installation

| Required download | Install / use | Availability |
| --- | --- | --- |
| [AW3 installer](../aw3/README.md#installation) | Install the frontend only; do not install the AW3 backend | Not yet published |
| SmartDocking algorithm `.tar.gz` | Deploy the algorithm package following its device installation instructions | Not yet published |

Both downloads are required. The AW3 installer is maintained under AW3; this application's new software Releases host the SmartDocking algorithm package only, without duplicating the AW3 installer. Compatible frontend, algorithm, and device versions must be specified with the published package.

## Start here

| Step | Resource |
| --- | --- |
| 1. Prepare the frontend and algorithm package | [Installation](#installation) |
| 2. Connect and configure the AW3 frontend | [AW3 User Manual](../aw3/docs/aw3-application-algorithm-platform-user-manual-v0.1.pdf) |
| 3. Review algorithm changes and calibration notes | [SmartDocking Release Notes](releases/README.md#smartdocking-301) |
| Configure camera networking and inspect point clouds | [LxCameraViewer](../tools/lxcameraviewer/README.md) |

<a id="latest-download"></a>

## Legacy PalletPro

PalletPro is a separate, earlier host application. It is not the AW3 frontend or the SmartDocking algorithm package. The following downloads and guide are retained for existing PalletPro deployments; their UI instructions do not describe the AW3 workflow.

<details>
<summary><strong>PalletPro downloads and user guide</strong></summary>

<p align="center">
  <a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe"><img src="../user-guides/assets/button-download-palletpro-latest.svg" alt="Download PalletPro 1.4.8_260828" width="240" height="40"></a>
  <a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/pallet-docking/docs/user-guide.md"><img src="../user-guides/assets/button-user-guide-large.svg" alt="Read the legacy PalletPro user guide" width="240" height="40"></a>
</p>

| Item | Details |
| --- | --- |
| Installer | [PalletPro-install-v1.4.8_260828.exe](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe) |
| File size | 118,296,332 bytes (112.82 MiB) |
| SHA-256 | `c1bcc40900eb0c3f282c5657a7c3d06b69629483ec1674f4da347a295485dc3c` |
| Version notes | [PalletPro 1.4.8_260828](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/pallet-docking/releases/README.md#palletpro-148-260828) |
| Historical package | [PalletPro_1.4.8.zip](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro_1.4.8.zip) |


</details>

[Complete Pallet Docking release history](releases/README.md)
