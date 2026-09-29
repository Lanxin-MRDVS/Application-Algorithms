# Volume Measurement Release Notes

[Documentation Home](../../README.md) / [Volume Measurement](../README.md) / Release Notes

This is the single release-note file for TorusMetric. The supplied notes were compiled on **2026-09-22**. The compilation date is not a software publication date. Volume Measurement is installed through the AW3 installer; no separate TorusMetric algorithm package is required.

| Version | Scope | Public release date | Package |
| --- | --- | --- | --- |
| [2.0.1](#torusmetric-201) | Cumulative algorithm capabilities and fixes | Not supplied | [AW3 installer](../../aw3/README.md#installation); exact bundled algorithm version not verified |

### Installation and package ownership

Use the [AW3 installer](../../aw3/README.md#installation) and install both frontend and backend. No separate TorusMetric algorithm `.tar.gz` is required. The current frontend installer is AW3 3.1.2. Its executable metadata does not establish the exact backend algorithm version.

<a id="torusmetric-201"></a>

## TorusMetric 2.0.1

The version identifies the algorithm independently of the AW3 frontend. This is a cumulative account, not a claim that every item was newly introduced by a single incremental update.

### Capabilities and improvements

- Supports up to five detection regions, with independent 3D bounds, minimum target size, filtering, and object-merging options.
- Outputs per-object length, width, height, center coordinates, angle, and bounding-box volume; supports point-cloud real-volume estimation and resolution settings.
- The companion UI provides a region overview, per-object results, region editing, and mm/cm/m display-unit switching.
- Supports multi-camera calibration and fused point-cloud input, with improved relationships between installation height, extrinsics, and detection-region coordinates.
- Provides common filtering presets and advanced filter parameters, with improved installation-height readback and default handling.
- Supports one-shot algorithm-data saving. Fixes cover the one-shot image-save command lifecycle, input selection, and out-of-bounds result point clouds.

### Companion UI maintenance

- Improved region-boundary validation to prevent invalid ranges from being cached or sent.
- Improved detection defaults, terminology, and linked parameter behavior. These UI fixes are delivered with the AW3 frontend.

### Upgrade notes

- Parameters use `regions`; read results from `result.<region-id>.TM[]`.
- Raw dimensions are in mm and raw volumes in mm³. Frontend unit switching changes the display only.
- Real volume is estimated from point clouds and is affected by occlusion, point-cloud quality, and resolution. Validate with on-site samples after deployment.

### Delivery and documentation

Formal delivery belongs to the corresponding AW3 release. This cumulative algorithm record does not establish the exact algorithm version in the separately obtained AW3 backend component. See the AW3 page for the current installer; the TorusMetric release date and verified bundle mapping remain unspecified. No standalone patch is declared by this record.

- [User Manual V0.1](../docs/torusmetric-user-manual-v0.1.pdf)
- [White Paper V0.1](../docs/torusmetric-white-paper-v0.1.pdf)

The documentation versions are unchanged. Their exact software-build applicability has not been verified.
