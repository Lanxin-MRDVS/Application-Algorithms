[Documentation Home](../README.md) / Volume Measurement

<div align="center">

# TorusMetric Volume Measurement

**AW3-based 3D dimension and volume measurement for fixed stations, large objects, and multi-camera layouts.**

</div>

<table>
  <tr>
    <td width="66%" valign="top">
      <strong>Designed for operational 3D measurement</strong><br><br>
      TorusMetric turns calibrated RGB-D point clouds into repeatable object dimensions and volume data. It is designed for fixed measurement stations in warehouses and automated lines, including palletized goods, packages, and large or irregular rigid objects. A single AW3 project can use one or multiple cameras and configure up to five detection areas.<br><br>
      <a href="docs/torusmetric-white-paper-v0.1.pdf"><img src="docs/images/torusmetric-deployment-scenes.png" alt="TorusMetric deployment scenes for warehouses, automated lines, and large objects" width="650"></a>
    </td>
    <td width="34%" valign="top">
      <strong>Release status</strong><br><br>
      <strong>Latest documentation</strong><br>
      <code>V0.1</code> · 2026-09-09<br>
      Formal version: <code>TBC</code><br>
      <a href="docs/torusmetric-user-manual-v0.1.pdf">User Manual</a> · <a href="docs/torusmetric-white-paper-v0.1.pdf">White Paper</a><br><br>
      <strong>Latest formal software</strong><br>
      Version: <code>TBC</code> · Planned<br>
      AW3: <code>TBC</code> · End of September 2026<br><br>
      <strong>Applicable standalone updates</strong><br>
      Not published<br><br>
      <a href="releases/README.md"><strong>View software version history →</strong></a><br><br>
      <small>Formal software is delivered with AW3. Only active updates for the latest formal version are shown here.</small>
    </td>
  </tr>
</table>

## How it works

The application captures one or more depth point clouds, applies the AW3 calibration, filters each detection area, separates objects, and calculates structured results. The optional **Real Volume** estimate uses surfaces visible to the cameras; it does not represent net material volume.

<p align="center">
  <a href="docs/torusmetric-white-paper-v0.1.pdf"><img src="docs/images/torusmetric-measurement-flow.png" alt="TorusMetric point-cloud processing and volume measurement flow" width="860"></a>
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

AW3 manages devices, camera groups, calibration, application settings, monitoring, and protocol output. TorusMetric runs as an AW3 application, calculates the measurement result, and passes configured data to the customer's business system.

<p align="center">
  <a href="docs/torusmetric-white-paper-v0.1.pdf"><img src="docs/images/torusmetric-aw3-workflow.png" alt="TorusMetric deployment from RGB-D cameras through AW3 to external business systems" width="860"></a>
</p>

## Start here

<table width="100%">
  <thead>
    <tr>
      <th width="65%">Step</th>
      <th width="35%">Link</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1. Review product fit</td>
      <td><a href="docs/torusmetric-white-paper-v0.1.pdf">White Paper V0.1</a></td>
    </tr>
    <tr>
      <td>2. Verify camera data</td>
      <td><a href="../tools/lxcameraviewer/README.md">LxCameraViewer</a></td>
    </tr>
    <tr>
      <td>3. Deploy and validate in AW3</td>
      <td><a href="docs/torusmetric-user-manual-v0.1.pdf">User Manual V0.1</a></td>
    </tr>
  </tbody>
</table>
