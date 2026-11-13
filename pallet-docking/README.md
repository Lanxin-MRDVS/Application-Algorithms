[Documentation Home](../README.md) / Pallet Docking

<div align="center">

# SmartDocking Pallet Docking

**Pallet entry-face position, orientation, and status for autonomous forklift docking.**

</div>

> **Before you update:** Check your installed AW3 and algorithm versions against the software history below. PalletPro users should use the legacy downloads and guide for their deployment.

<details>
<summary><strong>Legacy PalletPro</strong> · 1.4.8_260828 · downloads and user guide</summary>

<a id="legacy-palletpro"></a>
<a id="latest-download"></a>

PalletPro is a separate, earlier host application. It is not the AW3 frontend or the SmartDocking algorithm package. The following downloads and guide are retained for existing PalletPro deployments; their UI instructions do not describe the AW3 workflow.

| Item | Details |
| --- | --- |
| Installer | [PalletPro Installer](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe) |
| User guide | [PalletPro User Guide](docs/user-guide.md) |
| File size | 118,296,332 bytes (112.82 MiB) |
| SHA-256 | `c1bcc40900eb0c3f282c5657a7c3d06b69629483ec1674f4da347a295485dc3c` |
| Version notes | [PalletPro 1.4.8_260828](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/pallet-docking/releases/README.md#palletpro-148-260828) |
| Historical package | [PalletPro Archive (ZIP)](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro_1.4.8.zip) |

</details>

<details>
<summary><strong>Software history</strong> · SmartDocking / PalletPro</summary>

<a id="software-update-history"></a>

SmartDocking algorithm versions and legacy PalletPro host versions are separate components. All detailed notes remain in one [Release Notes](releases/README.md) file.

| Version | Category | Target | Publication date | Release note / download |
| --- | --- | --- | --- | --- |
| SmartDocking `3.0.2` | Device algorithm package | RKU20 / Linux ARM64; AW3 frontend | 2026-09-29 | [Notes](releases/README.md#smartdocking-302) · [SmartDocking Package](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/smartdocking-v3.0.2/SmartDocking-RKU20-V3.0.2_260929_linux_arm64.tar.gz) |
| PalletPro `1.4.8_260828` | Legacy standalone host | Windows | 2026-08-24 | [Notes](releases/README.md#palletpro-148-260828) · [Historical Release](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/tag/PalletPro) |

</details>

<details>
<summary><strong>Documentation</strong> · Latest English manuals and white papers</summary>

<a id="document-update-history"></a>

| Document | Version | Document date | Download |
| --- | --- | --- | --- |
| User Manual | V0.2 | 2026-10-30 | [Download PDF](https://raw.githubusercontent.com/Lanxin-MRDVS/Application-Algorithms/e123cfae91274642b46ad740c7d0505c007bd564/downloads/knowledge-community/current/pallet/MRDVS_Smart_Docking_User_Manual_v0_2.pdf) |
| White Paper | V0.2 | 2026-11-12 | [Download PDF](https://raw.githubusercontent.com/Lanxin-MRDVS/Application-Algorithms/e123cfae91274642b46ad740c7d0505c007bd564/downloads/knowledge-community/current/pallet/MRDVS_Smart_Docking_White_Paper_v0_2.pdf) |

Legacy PalletPro deployments: [PalletPro User Guide](docs/user-guide.md).

Document and software versions are managed separately.

</details>

<table>
  <tr>
    <td width="66%" valign="top">
      <strong>Designed for forklift pallet positioning</strong><br><br>
      SmartDocking locates the pallet fork-entry face using pure 3D geometry for the standard international offering. It supplies a reference position, orientation, and positioning status to the vehicle. AW3 manages devices, configuration, calibration, and result monitoring; the vehicle controller selects targets and controls motion and safety.<br><br>
      <img src="docs/images/smartdocking-applications.png" alt="Warehouse handling, production handover, and under-pallet handling" width="650">
    </td>
    <td width="34%" valign="top">
      <strong>Release status</strong><br><br>
      <strong>Latest documentation</strong><br>
      User Manual <code>V0.2</code> · 2026-10-30<br>
      White Paper <code>V0.2</code> · 2026-11-12<br>
      <a href="https://raw.githubusercontent.com/Lanxin-MRDVS/Application-Algorithms/e123cfae91274642b46ad740c7d0505c007bd564/downloads/knowledge-community/current/pallet/MRDVS_Smart_Docking_User_Manual_v0_2.pdf">User Manual</a> · <a href="https://raw.githubusercontent.com/Lanxin-MRDVS/Application-Algorithms/e123cfae91274642b46ad740c7d0505c007bd564/downloads/knowledge-community/current/pallet/MRDVS_Smart_Docking_White_Paper_v0_2.pdf">White Paper</a><br><br>
      <strong>Latest algorithm package</strong><br>
      SmartDocking <code>3.0.2</code><br>
      2026-09-29 · RKU20 / Linux ARM64<br>
      <a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/smartdocking-v3.0.2/SmartDocking-RKU20-V3.0.2_260929_linux_arm64.tar.gz">SmartDocking Package</a> · <a href="releases/README.md#smartdocking-302">Release notes</a><br><br>
      <strong>Required frontend</strong><br>
      <a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/aw3-v3.1.2/AW3-V3.1.2_260929_win_x64.exe">AW3 Installer</a><br>
      Frontend only; no AW3 PC backend<br><br>
      <a href="#user-content-software-update-history"><strong>View software history ↑</strong></a><br>
      <a href="#user-content-document-update-history">View document history ↑</a>
    </td>
  </tr>
</table>

## How it works

Pure 3D positioning matches leg and beam geometry against a configured template. Configure and calibrate the template for the site pallets. The V0.2 documents cover the standard international offering; 2D semantic positioning is not included.

<p align="center"><img src="docs/images/smartdocking-positioning-flow.png" alt="Semantic and pure 3D positioning paths, reference point, and valid result fields" width="860"></p>

## Outputs and capabilities

| Output or capability | Purpose |
| --- | --- |
| Entry-face reference position | X, Y, and Z in millimeters for the pallet fork-entry reference point. |
| Orientation | Roll and Yaw in degrees; Pitch is fixed at zero and is not a valid measured output. |
| Positioning status | Check validity, detected count, and available pallet-class results before vehicle use. |
| Pure 3D positioning | Configure a geometry template for the site pallets. |
| Pallet templates and calibration | Maintain pallet geometry and installation-specific settings. |
| Load detection | Available in pure 3D mode when enabled; it is not a general 2D output. |

Validate the installed camera, pallet types, entry-face visibility, calibration, and complete vehicle docking behavior. Model coverage and geometry settings must match the site's pallets; this page does not claim universal recognition or collision safety.

## Installation

| Download | Target | Installation |
| --- | --- | --- |
| [AW3 Installer](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/aw3-v3.1.2/AW3-V3.1.2_260929_win_x64.exe) | Windows x64 PC | Install the frontend only; clear **AW3 Backend Download**. |
| [SmartDocking Package](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/smartdocking-v3.0.2/SmartDocking-RKU20-V3.0.2_260929_linux_arm64.tar.gz) | RKU20, Linux ARM64 | Deploy the `.tar.gz` to the matching device / center via SSH, following the User Manual. |

Both packages are required. Do not install the AW3 PC backend for this application. The algorithm archive contains the device-side service and runtime dependencies; it is not a Windows installer. Confirm the device platform before updating and back up its configuration. Hardware deployment has not been tested as part of this publication.

## Start here

<table>
  <thead><tr><th width="620" align="left">Step</th><th width="240" align="left">Link</th></tr></thead>
  <tbody>
    <tr><td>1. Review application fit and operating limits</td><td><a href="https://raw.githubusercontent.com/Lanxin-MRDVS/Application-Algorithms/e123cfae91274642b46ad740c7d0505c007bd564/downloads/knowledge-community/current/pallet/MRDVS_Smart_Docking_White_Paper_v0_2.pdf">White Paper</a></td></tr>
    <tr><td>2. Install the AW3 frontend and the device algorithm package</td><td><a href="#installation">Installation</a></td></tr>
    <tr><td>3. Configure, calibrate, and validate the application</td><td><a href="https://raw.githubusercontent.com/Lanxin-MRDVS/Application-Algorithms/e123cfae91274642b46ad740c7d0505c007bd564/downloads/knowledge-community/current/pallet/MRDVS_Smart_Docking_User_Manual_v0_2.pdf">User Manual</a></td></tr>
  </tbody>
</table>
