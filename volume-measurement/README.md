# TorusMetric Volume Measurement

[Documentation Home](../README.md) / Volume Measurement

<p align="center"><strong>AW3-based 3D dimension and volume measurement for fixed stations, large objects, and multi-camera layouts.</strong></p>

<p align="center">
  <a href="docs/torusmetric-user-manual-v0.1.pdf"><img src="../user-guides/assets/button-torusmetric-user-manual.svg" alt="Open the TorusMetric User Manual" width="240" height="40"></a>
  <a href="docs/torusmetric-white-paper-v0.1.pdf"><img src="../user-guides/assets/button-torusmetric-white-paper.svg" alt="Open the TorusMetric White Paper" width="240" height="40"></a>
  <a href="../aw3/releases/README.md"><img src="../user-guides/assets/button-aw3-release-history.svg" alt="Open the AW3 release history" width="240" height="40"></a>
</p>

TorusMetric uses RGB-D point clouds to calculate length, width, height, bounding-box volume, and an optional visible-surface volume estimate. It supports single-camera and multi-camera deployments with up to five detection areas.

## Release status

| Item | Status | Location |
| --- | --- | --- |
| Product documentation | `V0.1` · Published 2026-09-09 | [User Manual](docs/torusmetric-user-manual-v0.1.pdf) · [White Paper](docs/torusmetric-white-paper-v0.1.pdf) |
| Formal software release | Planned with the AW3 release at the end of September 2026 | [AW3 release history](../aw3/releases/README.md) |
| Volume Measurement patch | No public patch package yet | [Patch and version history](releases/README.md) |

No software package is linked until its AW3 release or patch package is published and verified.

## What TorusMetric measures

| Output or capability | Purpose |
| --- | --- |
| Length, width, and height | Centimeter-class dimensioning for packaging, loading, and space assessment. |
| Bounding-box volume | Occupied-space estimate calculated from object dimensions. |
| Real Volume | Optional estimate based on surfaces visible to the cameras; not net material volume or a billing measurement. |
| Multi-camera stitching | Extends coverage and reduces blind spots for large or oversized objects. |
| Multiple detection areas | Supports one to five areas with per-object or merged output. |
| AW3 data output | Sends configured results to WMS, TMS, ERP, MES, PLC, or other project systems. |

Final performance depends on the installation, camera layout, point-cloud quality, calibration, object surface, occlusion, and project acceptance criteria. Use representative and boundary samples for validation.

## Start here

| Task | Resource |
| --- | --- |
| Evaluate capabilities, scope, and operating limits | [TorusMetric White Paper V0.1](docs/torusmetric-white-paper-v0.1.pdf) |
| Install, calibrate, configure, and validate the application | [TorusMetric User Manual V0.1](docs/torusmetric-user-manual-v0.1.pdf) |
| Review document files and verification data | [Documentation index](docs/README.md) |
| Track the formal production package | [AW3 release history](../aw3/releases/README.md) |
| Track application-specific fixes | [Volume Measurement patch history](releases/README.md) |
| Configure cameras and inspect point clouds | [LxCameraViewer](../tools/lxcameraviewer/README.md) |
| Integrate camera data | [CameraSDK](https://github.com/Lanxin-MRDVS/CameraSDK) |

## Release model

Formal TorusMetric versions are delivered as part of AW3 and recorded in the AW3 release history. Short-cycle fixes that must be distributed independently are recorded in this application's `releases/` folder with their compatible AW3 version, package, checksum, release note, and rollback guidance. Previous rows are retained when new versions are added.
