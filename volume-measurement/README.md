[Documentation Home](../README.md) / Volume Measurement

<div align="center">

# TorusMetric Volume Measurement

**AW3-based 3D dimension and volume measurement for fixed stations, large objects, and multi-camera layouts.**

</div>

> **Before you update:** Check your installed AW3 and algorithm versions against the software history below. Confirm that the document version applies to your deployment before following installation or configuration steps.

<details>
<summary><strong>Software history</strong> · TorusMetric version records</summary>

<a id="software-update-history"></a>

This table retains formal versions and standalone updates. The supplied TorusMetric 2.0.1 notes describe cumulative algorithm capabilities; they do not identify a published AW3 bundle or a standalone patch package.

| Version | Category | Formal baseline | AW3 | Release date | Status / supersedes | Release note / download |
| --- | --- | --- | --- | --- | --- | --- |
| `2.0.1` | AW3-bundled algorithm | Not verified | Not verified | Not supplied | Algorithm notes available; exact AW3 bundle mapping not verified | [Release notes](releases/README.md#torusmetric-201) |

- **Formal software** is delivered with AW3 and becomes the application baseline.
- **Standalone update** is a patch for a named formal baseline and compatible AW3 version. Its status shows whether it is active or superseded.

</details>

<details>
<summary><strong>Document history</strong> · V0.1</summary>

<a id="document-update-history"></a>

The Release status shows the latest document set. This table retains every published document version and its software applicability.

| Document | Version | Applies to | Publication date | Status | File |
| --- | --- | --- | --- | --- | --- |
| TorusMetric User Manual | `V0.1` | Formal: `TBC`<br>Standalone: none<br>AW3: `TBC` | 2026-09-09 | Current | [PDF](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/volume-measurement/docs/torusmetric-user-manual-v0.1.pdf) |
| TorusMetric Volume Measurement Solution White Paper | `V0.1` | Formal: `TBC`<br>Standalone: none<br>AW3: `TBC` | 2026-09-09 | Current | [PDF](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/volume-measurement/docs/torusmetric-white-paper-v0.1.pdf) |

</details>

<table>
  <tr>
    <td width="66%" valign="top">
      <strong>Designed for operational 3D measurement</strong><br><br>
      TorusMetric turns calibrated RGB-D point clouds into repeatable object dimensions and volume data. It is designed for fixed measurement stations in warehouses and automated lines, including palletized goods, packages, and large or irregular rigid objects. A single AW3 project can use one or multiple cameras and configure up to five detection areas.<br><br>
      <img src="docs/images/torusmetric-deployment-scenes.png" alt="TorusMetric deployment scenes for warehouses, automated lines, and large objects" width="650">
    </td>
    <td width="34%" valign="top">
      <strong>Release status</strong><br><br>
      <strong>Latest documentation</strong><br>
      <code>V0.1</code> · 2026-09-09<br>
      Formal version: <code>TBC</code><br>
      <a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/volume-measurement/docs/torusmetric-user-manual-v0.1.pdf">User Manual</a> · <a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/volume-measurement/docs/torusmetric-white-paper-v0.1.pdf">White Paper</a><br><br>
      <strong>Latest formal software</strong><br>
      <a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/aw3-v3.1.2/AW3-V3.1.2_260929_win_x64.exe">AW3 Installer</a> · 2026-09-29<br>
      Recorded algorithm: <a href="releases/README.md#torusmetric-201">TorusMetric 2.0.1</a><br>
      Delivery: AW3 installer (frontend + backend)<br><br>
      <strong>Applicable standalone updates</strong><br>
      Not published<br><br>
      <a href="#user-content-software-update-history"><strong>View software history ↑</strong></a><br>
      <a href="#user-content-document-update-history">View document history ↑</a><br><br>
      <small>Download AW3 only and install both frontend and backend. No separate TorusMetric algorithm package is required.</small>
    </td>
  </tr>
</table>

## How it works

The application captures one or more depth point clouds, applies the AW3 calibration, filters each detection area, separates objects, and calculates structured results. The optional **Real Volume** estimate uses surfaces visible to the cameras; it does not represent net material volume.

<p align="center">
  <img src="docs/images/torusmetric-measurement-flow.png" alt="TorusMetric point-cloud processing and volume measurement flow" width="860">
</p>

## Outputs and capabilities

| Output or capability | Purpose |
| --- | --- |
| Length, width, and height | Centimeter-class dimensioning for packaging, loading, and space assessment. |
| Bounding-box volume | Occupied-space estimate calculated from object dimensions. |
| Real Volume | Optional visible-surface estimate for supported project scenarios. |
| Multi-camera stitching | Extends coverage and reduces blind spots for large or oversized objects. |
| Multiple detection areas | Supports one to five areas with per-object or merged output. |
| Structured data output | Sends configured results to WMS, TMS, ERP, MES, PLC, or another project system. |

Final performance depends on the installation, camera layout, point-cloud quality, calibration, object surface, occlusion, and project acceptance criteria. TorusMetric is intended for centimeter-class operational measurement, not millimeter metrology, billing, or net material volume. Validate representative and boundary samples in the final layout.

## AW3 deployment

**Download the [AW3 installer](../aw3/README.md#installation) only. Install both the AW3 frontend and backend.** Volume Measurement does not require a separate algorithm `.tar.gz`. The current download is [AW3 Installer](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/aw3-v3.1.2/AW3-V3.1.2_260929_win_x64.exe).

AW3 manages devices, camera groups, calibration, application settings, monitoring, and protocol output. TorusMetric runs as an AW3 application, calculates the measurement result, and passes configured data to the customer's business system.

<p align="center">
  <img src="docs/images/torusmetric-aw3-workflow.png" alt="TorusMetric deployment from RGB-D cameras through AW3 to external business systems" width="860">
</p>

## Start here

<table>
  <thead>
    <tr>
      <th width="620" align="left">Step</th>
      <th width="240" align="left">Link</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1. Review product fit</td>
      <td><a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/volume-measurement/docs/torusmetric-white-paper-v0.1.pdf">White Paper</a></td>
    </tr>
    <tr>
      <td>2. Verify camera data</td>
      <td><a href="../tools/lxcameraviewer/README.md">LxCameraViewer</a></td>
    </tr>
    <tr>
      <td>3. Deploy and validate in AW3</td>
      <td><a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/volume-measurement/docs/torusmetric-user-manual-v0.1.pdf">User Manual</a></td>
    </tr>
  </tbody>
</table>
