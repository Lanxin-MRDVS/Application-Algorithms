# Depalletizing Release Notes

[Documentation Home](../../README.md) / [Depalletizing](../README.md) / Release Notes

This is the single release-note file for Depalletizing. It retains the public standalone-package history and the independently versioned PalletEye algorithm record. The new source notes were compiled on **2026-09-22**; that date is not a release date.

| Component / version | Scope | Public package |
| --- | --- | --- |
| [PalletEye 3.0.1](#palleteye-301) | Cumulative algorithm record supplied in September 2026 | No matching package supplied with this record |
| [Legacy standalone 3.0.1](#legacy-standalone-301) | Existing public delivery, published 2026-07-03 | [ZIP package](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/Depalletizing-Algorithm-V3.0.1/AW3-V3.0.1-20260624.zip) |

The shared `3.0.1` number does not prove that the legacy ZIP contains the cumulative PalletEye changes below. Check the component manifest for the specific delivery.

<a id="palleteye-301"></a>

## PalletEye 3.0.1

**Scope:** Cumulative capabilities and fixes under the algorithm's independent version. **Public release date and matching package:** Not supplied.

### Templates and calibration

- Centralizes product templates, size ranges, working regions, hand-eye extrinsics, and single-trigger operation.
- Supports copying the current region and calibration to other templates while preserving unmodified templates and extension fields.
- The companion frontend separates depalletizing hand-eye calibration from platform extrinsics to reduce interference between calibration settings.

### Detection and stability

- Applies clustering-based denoising to merged package point clouds, reducing the effect of image/depth edge differences on geometric measurements.
- Improves height-boundary checks and mask/target out-of-region states; fixes incorrect blocking behavior when safety checks are disabled.
- Supports reuse of the same model across cameras and queued inference, isolating request parameters and results; fixes template-keyword interference between cameras.
- Improves detection-parameter retention and diagnostics for empty images, model-loading failures, and other exceptions.

### Protocols and deployment

- Provides the `3D;` semicolon protocol and HNPS-A rule template, with configurable result counts, coordinate directions, and orientation-angle rules.
- Improves zero-package responses and angle output, and supports creation of dedicated backend update packages.

### Upgrade notes

- Check templates, hand-eye extrinsics, working regions, and safety-detection settings after upgrading.
- During robot or host-system integration, verify zero-package responses, counts, coordinate signs, and orientation-angle conventions.
- This is a cumulative description, not a list of changes all introduced relative to 3.0.0. Differences from older deliveries must be checked against their component manifests.

<a id="legacy-standalone-301"></a>

## Legacy standalone 3.0.1

The following record describes the existing public ZIP and retains its original publication and delivery scope.

| Item | Details |
| --- | --- |
| Product | Depalletizing |
| Version | `3.0.1` |
| Release-note date | 2026-06-24 |
| GitHub publication date | 2026-07-03 |
| Release type | Standalone application package |
| Stability | Stable |
| Delivery status | Current public package (legacy standalone architecture) |
| Target delivery | AW3 |
| AW3 compatibility | Not applicable; this is not an AW3-integrated release |
| Historical tag | `Depalletizing-Algorithm-V3.0.1` |

### Overview

Depalletizing `3.0.1` delivers improvements for custom stack categories and automatic region calibration, together with a layer-positioning defect fix. Although the published asset filename contains `AW3`, the confirmed delivery runs independently outside AW3. The historical filename, tag, and asset URL are retained for compatibility.

### New features

#### Custom stack categories

- Added custom stack categories for white bags and other objects not reliably covered by the default recognition categories.
- Supports descriptions based on distinctive color and texture characteristics.
- Available labels include `Bag`, `Box`, and `White object and bag`.
- Added a configuration warning requiring recognition verification before production operation.

#### Automatic region calibration

- Added a minimum stack-size threshold for automatic region calibration.
- Excludes stacks below the configured threshold from region selection to reduce false calibration caused by small objects.
- The threshold is configured by deployment personnel and is not exposed in the end-user interface.

### Fixes

- Fixed positioning errors caused by overlapping size ranges between adjacent layers during layer determination.

### Compatibility and verification

The supplied historical record does not identify a supported operating-system matrix, camera firmware range, complete application-version manifest, or verified rollback procedure. These remain **Not verified** and must not be inferred from the package filename. Package size and SHA-256 below are recorded from the existing GitHub Release asset; this documentation update did not run the software.

### Upgrade guidance

1. Back up the current standalone application package, task templates, configurations, and calibration data.
2. Install or extract the published package using the approved project procedure.
3. Run a single-trigger recognition test and confirm positioning results before resuming automatic operation.
4. Validate custom categories using representative objects from the actual operating environment.

### Known operational notes

- Keep category descriptions concise and focused on distinctive color or texture characteristics.
- MobaXterm and NetAssist are optional third-party deployment tools and are not included in this release.

### Downloads

| Asset | Size | SHA-256 | Download |
| --- | ---: | --- | --- |
| `AW3-V3.0.1-20260624.zip` | 188,966,241 bytes | `9031fabf8aabf5e024886f259dd4db7e9255faa176b28c113ca6b5f870c91851` | [Download](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/Depalletizing-Algorithm-V3.0.1/AW3-V3.0.1-20260624.zip) |

- [Historical GitHub Release](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/tag/Depalletizing-Algorithm-V3.0.1)
- [Depalletizing deployment guide](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/depalletizing/docs/deployment-guide.md)
