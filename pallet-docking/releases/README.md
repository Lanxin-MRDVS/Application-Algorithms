# Pallet Docking Release Notes

[Documentation Home](../../README.md) / [Pallet Docking](../README.md) / Release Notes

This is the single release-note file for Pallet Docking. SmartDocking algorithm versions and PalletPro host-application versions are tracked separately in this file. The new algorithm notes were compiled on **2026-09-22**; this is not their software publication date.

| Component / version | Scope | Public package |
| --- | --- | --- |
| [SmartDocking 3.0.1](#smartdocking-301) | Algorithm update relative to 2.0.1 | Not supplied with this record |
| [PalletPro 1.4.8_260828](#palletpro-148-260828) | Existing standalone Windows host application | [Windows installer](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe) |

A PalletPro version does not identify the SmartDocking algorithm installed on the device. The source notes do not establish a new public SmartDocking package or a verified AW3 bundle manifest.

### Installation and package ownership

For SmartDocking, use the [AW3 installer](../../aw3/README.md#installation) for the frontend only, plus the SmartDocking algorithm `.tar.gz`. Do not install the AW3 backend. New SmartDocking software Releases own only the algorithm package; legacy PalletPro installers remain available in their existing Release.

<a id="smartdocking-301"></a>

## SmartDocking 3.0.1

**Scope:** Pallet detection and calibration changes relative to 2.0.1. **Public release date:** Not supplied.

### Semantic pallet detection

- Uses HydraV3 and YOLO26 instance-segmentation models with 3D pallet detection based on the segmentation results.
- Simplifies detection parameters and adds two-leg and four-leg pallet detection. Detection follows the leg count identified by semantic segmentation.

### Pure 3D pallet detection

- Retains the pure 3D pipeline and improves handling of clearly abnormal detections.
- Supports detection in the order three legs, two legs, then four legs.
- Adds ground estimation during calibration and supports multi-level detection results.

### Calibration and companion operations

- Both semantic and pure 3D modes support calibration using near and far captures.
- Pure 3D calibration supports sending the ground-height result.
- The companion AW3 interface provides detection-mode, template, installation-orientation, extrinsic, and result management.
- The newer companion frontend displays load state, reporting unknown when the device does not return that field.

### Upgrade notes

- Use matching device algorithms, inference runtimes, and model files. The Windows configuration interface does not imply a local inference environment.
- AI mode follows the segmented leg count; pure 3D mode follows the three-leg, two-leg, four-leg sequence. Their parameters are not interchangeable.
- Read back templates and calibration results, then revalidate near/far operation and installation orientation.
- Detection time depends on hardware, input, and model. No universal performance figure is claimed.

<a id="palletpro-148-260828"></a>

## PalletPro 1.4.8_260828

The following record retains the existing public host-application release and its original scope.

| Item | Details |
| --- | --- |
| Product | PalletPro |
| Full version | `1.4.8_260828` |
| Publication date | 2026-08-24 |
| Release type | Standalone Pallet Docking tool |
| Stability | Stable |
| Platform | Windows; supported Windows versions not verified |
| Compatible AW3 versions | Not applicable |
| Installer | [PalletPro-install-v1.4.8_260828.exe](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe) |
| File size | 118,296,332 bytes (112.82 MiB) |
| Downloads | [PalletPro Release](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/tag/PalletPro) |
| User guide | [Pallet Docking User Guide — Eagle-M Series Cameras](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/pallet-docking/docs/user-guide.md) |

### Overview

PalletPro `1.4.8_260828` focuses on English-language usability for camera configuration, pallet docking and calibration, and parameter editing. This update adds English text for previously untranslated interface elements and refines terminology across the documented workflows.

### Improvements and fixes

| Area | User-visible changes |
| --- | --- |
| Main interface and common dialogs | Added English text for docking operations, external calibration, frame-rate modes, trajectory downloads, firmware-upgrade status, and common prompts. |
| Camera management | Added English labels and messages for camera information, log downloads, application-parameter transfers, embedded-algorithm upgrades, configuration-file operations, and camera reboot status. |
| Pallet teaching and calibration | Added English teaching instructions, setup guidance, validation messages, and error prompts for near/far teaching and secondary calibration. These entries describe message and instruction updates, not changes to calibration logic. |
| Advanced parameter settings | Added English labels for pallet-leg width, crossbar detection, and pallet width, together with descriptions of pose, detection-region, geometry, and filtering parameters. |
| Algorithm parameter dialogs | Added English text for the existing Plane Detection, Cage Stacking, and Reel Docking configuration interfaces, including parameter import, export, and save messages. |
| Structured JSON Editor | Added English controls and prompts for field editing, data-type validation, missing or duplicate keys, file-format checks, algorithm selection, and workstation selection. |
| Config Tools | Added English parameter descriptions for application IDs, network ports, configuration paths, filtering, segmentation, and coordinate frames. |

### Terminology updates

Two frequently used controls now use clearer English labels:

| Previous label | Updated label |
| --- | --- |
| `High Adaptability` | `Auto-adjusting height` |
| `Parameter Settings` | `Camera Position Settings` |

Mounting-orientation wording has also been revised to identify upright installation with the logo on top, left/right 90-degree rotation, and upside-down installation more clearly.

### Known limitation

Structured JSON Editor V2024 does not support Chinese content input. English interface localization does not remove this input limitation.

### Upgrade guidance

1. Back up existing application settings, algorithm configuration files, and calibration data before updating.
2. Use the Windows installer linked above. Keep the earlier package and configuration backups available for recovery.
3. After updating, verify camera connection, configuration loading, English interface text, and recognition results with the existing calibration before returning to normal operation. Follow the commissioning requirements for the actual installation.

The documented changes concern interface text and parameter descriptions. No algorithm, communication-protocol, or configuration-schema changes are identified in the supplied change record; this does not constitute a compatibility guarantee for an unverified camera firmware or embedded-algorithm version.

### Compatibility and rollback

- Supported camera firmware and embedded-algorithm versions were not identified in the supplied change record and remain **Not verified**.
- No breaking algorithm, communication-protocol, or configuration-schema change is documented for this build.
- To roll back, restore the earlier PalletPro package together with the configuration and calibration backup created before the upgrade. A separately validated automated rollback procedure was not supplied.

### Package verification

**SHA-256**

```text
c1bcc40900eb0c3f282c5657a7c3d06b69629483ec1674f4da347a295485dc3c
```

Verify the downloaded installer in PowerShell:

```powershell
Get-FileHash -LiteralPath '.\PalletPro-install-v1.4.8_260828.exe' -Algorithm SHA256
```

**Historical reference:** [Detailed localization change record, dated 2026-08-21](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/dc7e5dc1f85cd6212fcc8576d34c7dd25cc36da8/PalletProUpdateNote.md). The earlier record date is retained for traceability and is not used as the release date of this installer.
