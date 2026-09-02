# Pallet Docking

[Documentation Home](../README.md) / Pallet Docking

Pallet Docking provides pallet recognition and precise forklift docking for MRDVS Eagle-M series cameras. The current public workflow uses the PalletPro Windows application for camera configuration, pallet teaching, calibration, parameter management, and result integration.

| Status | Value |
| --- | --- |
| Current tool | PalletPro |
| Latest public build | `1.4.8_260828` |
| Current platform | Windows |
| Target runtime | AW3 |

## Latest download

<p align="center">
  <a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe"><img src="../user-guides/assets/button-download-palletpro-latest.svg" alt="Download PalletPro 1.4.8_260828" width="240" height="40"></a>
  <a href="docs/user-guide.md"><img src="../user-guides/assets/button-user-guide-large.svg" alt="Read the Pallet Docking user guide" width="240" height="40"></a>
</p>

| Item | Details |
| --- | --- |
| Installer | [PalletPro-install-v1.4.8_260828.exe](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe) |
| File size | 118,296,332 bytes (112.82 MiB) |
| SHA-256 | `c1bcc40900eb0c3f282c5657a7c3d06b69629483ec1674f4da347a295485dc3c` |
| Version notes | [PalletPro 1.4.8_260828](releases/v1.4.8_260828.md) |
| Historical package | [PalletPro_1.4.8.zip](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro_1.4.8.zip) |

## Start here

| Task | Resource |
| --- | --- |
| Install and verify PalletPro | [Latest download](#latest-download) |
| Install the camera and perform teaching or calibration | [User guide](docs/user-guide.md#4-initial-setup-and-calibration-going-through) |
| Integrate API, UDP, TCP, or CAN results | [Communication guide](docs/user-guide.md#5-data-communication-methods) |
| Configure the camera network and inspect point clouds | [LxCameraViewer](../tools/lxcameraviewer/README.md) |
| Review every published version | [Pallet Docking release history](releases/README.md) |

## Lifecycle

The existing standalone PalletPro release remains available for current deployments. Pallet Docking is planned to move into AW3. When that transition is released, the shared platform version will be recorded in the [AW3 release history](../aw3/releases/README.md), while Pallet Docking-only patches will remain under this application's `releases/` directory and declare AW3 compatibility.
