<p align="center"><img src="assets/mrdvs-logo-en.webp" alt="MRDVS Mobile Robot Vision Expert" width="360"></p>

<h1 align="center">MRDVS Application Algorithms</h1>

<p align="center"><strong>Application documentation, verified downloads, and release history for MRDVS 3D vision products.</strong></p>

<p align="center">
  <a href="applications/depalletizing/README.md"><img src="assets/button-depalletizing.svg" alt="Depalletizing" width="160" height="36"></a>
  <a href="applications/pallet-docking/README.md"><img src="assets/button-pallet-docking.svg" alt="Pallet Docking" width="160" height="36"></a>
  <a href="applications/volume-measurement/README.md"><img src="assets/button-volume-measurement.svg" alt="Volume Measurement" width="160" height="36"></a>
  <a href="applications/slot-monitoring/README.md"><img src="assets/button-slot-monitoring.svg" alt="Slot Monitoring" width="160" height="36"></a>
  <a href="applications/obstacle-avoidance/README.md"><img src="assets/button-obstacle-avoidance.svg" alt="Obstacle Avoidance" width="160" height="36"></a>
</p>

## Latest downloads

<p align="center">
  <a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/Depalletizing-Algorithm-V3.0.1/AW3-V3.0.1-20260624.zip"><img src="assets/button-download-aw3.svg" alt="Download AW3 3.0.1" width="240" height="40"></a>
  <a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe"><img src="assets/button-download-palletpro-latest.svg" alt="Download PalletPro 1.4.8_260828" width="240" height="40"></a>
  <a href="RELEASES.md"><img src="assets/button-release-history.svg" alt="View all release history" width="240" height="40"></a>
</p>

| Product | Latest public version | Distribution | Release notes |
| --- | --- | --- | --- |
| **AW3** | `3.0.1` | [Download platform package](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/Depalletizing-Algorithm-V3.0.1/AW3-V3.0.1-20260624.zip) | [AW3 3.0.1](platform/aw3/releases/v3.0.1.md) |
| **PalletPro** | `1.4.8_260828` | [Download Windows installer](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe) | [PalletPro 1.4.8_260828](applications/pallet-docking/releases/v1.4.8_260828.md) |

Packages are stored in **GitHub Releases**, not in the Git source tree. The [central release index](RELEASES.md) records current and historical versions without hiding earlier download links.

## Application delivery model

<p align="center"><img src="assets/aw3-application-model.svg" alt="Target delivery model showing Depalletizing, Pallet Docking, Volume Measurement, and Slot Monitoring on AW3; Obstacle Avoidance remains a camera application; shared camera tools are separate" width="820"></p>

AW3 is the target runtime for **Depalletizing, Pallet Docking, Volume Measurement, and Slot Monitoring**. Major platform releases are published under AW3. Short-cycle fixes and feature packages are versioned under the affected application and declare their compatible AW3 range. Obstacle Avoidance remains documented as a camera application until a different verified distribution model is published.

## Applications

| Application | Runtime and scope | Documentation | Version history |
| --- | --- | --- | --- |
| **Depalletizing** | AW3 application for soft-bag and carton unstacking. | [Overview](applications/depalletizing/README.md) · [Deployment guide](applications/depalletizing/docs/deployment-guide.md) | [Releases](applications/depalletizing/releases/README.md) |
| **Pallet Docking** | Pallet recognition and forklift docking; currently configured with PalletPro, with AW3 as the target runtime. | [Overview](applications/pallet-docking/README.md) · [User guide](applications/pallet-docking/docs/user-guide.md) | [Releases](applications/pallet-docking/releases/README.md) |
| **Volume Measurement** | 3D dimension and volume measurement; planned for AW3 distribution. | [Overview](applications/volume-measurement/README.md) | [Releases](applications/volume-measurement/releases/README.md) |
| **Slot Monitoring** | Storage-location placement and occupancy monitoring; planned for AW3 distribution. | [Overview](applications/slot-monitoring/README.md) · [User guide](applications/slot-monitoring/docs/user-guide.md) | [Releases](applications/slot-monitoring/releases/README.md) |
| **Obstacle Avoidance** | Camera-side obstacle detection, zones, and communication outputs. | [Overview](applications/obstacle-avoidance/README.md) · [Deployment guide](applications/obstacle-avoidance/docs/deployment-guide.md) | [Releases](applications/obstacle-avoidance/releases/README.md) |

## Platform and developer resources

| Area | Resource | Purpose |
| --- | --- | --- |
| Platform | [AW3](platform/aw3/README.md) | Platform downloads, major-version history, and application delivery model. |
| Camera tool | [LxCameraViewer](tools/lxcameraviewer/README.md) | Camera connection, network setup, and image or point-cloud inspection. |
| SDK | [CameraSDK](https://github.com/Lanxin-MRDVS/CameraSDK) | SDK packages, APIs, and integration examples. |
| Maintenance | [Release policy](docs/release-policy.md) | Version, tag, package, release-note, checksum, and compatibility rules. |
| Repository | [Repository structure](docs/repository-structure.md) | Required folder layout and the responsibility of each file. |

## Repository layout

```text
applications/   Application overviews, guides, assets, and per-application history
platform/       AW3 platform documentation and major releases
tools/          Shared deployment and camera tools
docs/           Repository and release-maintenance standards
assets/         Shared MRDVS brand and homepage graphics
RELEASES.md     Central index for every public package
```

Every application folder has the same public contract: `README.md` is the entry page, `docs/` stores technical guides, and `releases/` stores version history. See [applications/README.md](applications/README.md) for the complete developer-facing index.

---

<sub>Hangzhou Lanxin Technology Co., Ltd. & MRDVS Co., Ltd. · All Rights Reserved. · Last updated: September 2026</sub>
