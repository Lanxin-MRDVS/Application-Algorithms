# AW3 Release Notes

[Documentation Home](../../README.md) / [AW3](../README.md) / Release Notes

This is the single release-note file for AW3. Versions are retained below, newest first. The supplied notes were compiled on **2026-09-22**; that date is not the publication date of every version. No new installer was supplied with these notes, and no AW3 installer is currently published in this repository.

| Version | Scope | Public package in this repository |
| --- | --- | --- |
| [3.1.1](#aw3-311) | AW3Viewer Windows x64 frontend; 2026-09-22 build reference | Not published |
| [3.1.0](#aw3-310) | Initial delivery and later maintenance builds with the same version | Not published |
| [3.0.1](#aw3-301) | New AW3Viewer UI and cumulative platform changes from the legacy UI baseline | Not published |
| [Legacy UI](#legacy-ui) | AlgPlatformViewer baseline; no additional version number assigned | Not published |

AW3 frontend, device service, and algorithm versions are independent. Matching version numbers do not establish that components belong to the same package. Application manifests and package-specific compatibility must be checked separately.

### Installation and package ownership

Volume Measurement uses the AW3 installer with both frontend and backend. Slot Monitoring and Pallet Docking use the AW3 frontend only plus their separate algorithm `.tar.gz`; do not install the AW3 backend for those applications. See [installation requirements](../README.md#installation). This delivery model does not verify the contents or compatibility of any unpublished installer.

<a id="aw3-311"></a>

## AW3 3.1.1

**Component:** AW3Viewer, Windows x64 frontend. **Build reference:** 2026-09-22. **Public release date:** Not supplied.

### Changes

- Integrated a Batch Tools entry in the main menu for algorithm parameter management, batch service upgrades, and protocol uploads.
- Made the pallet-detection page more compact, grouped advanced settings into templates, and retained positioning-mode and detection-configuration controls.
- Showed parameters according to the selected pallet-detection mode, keeping P3D-only templates and ground-height settings out of other modes.
- Added loaded, unloaded, and unknown load states to pallet monitoring. The display reports unknown when the device does not return the field.
- Improved MDS camera preset application and linked the reset options when loading the relevant templates.

### Continued support

Retains the independent algorithm pages, slot configuration and monitoring, calibration, log export, and permission management from later AW3 3.1.0 maintenance builds.

### Upgrade notes

- This entry describes the frontend installer. Installing the frontend does not automatically upgrade the device service or algorithms.
- Load-state display and similar results depend on fields returned by the device.
- The volume-box orientation fix belongs to StockSync 3.1.1. MDS frame acquisition and pairing fixes belong to the corresponding camera backend. Install the appropriate device update separately.

<a id="aw3-310"></a>

## AW3 3.1.0

**Scope:** AW3 3.0.1 to 3.1.0. The initial delivery and subsequent maintenance builds share the same version number. **Public release dates:** Not supplied.

### Initial delivery

- Added pallet-docking configuration and monitoring, including results and error information.
- Added near/far two-stage pallet calibration, installation orientation, and extrinsic configuration; improved separate transmission of rotation and translation parameters.
- Added model management, orderly service shutdown, and log export across the full time range.
- Added protocol-rule uploads and full-package upgrades over SSH to the batch tools; improved Linux user-data migration.
- Filtered protocol capabilities by the active algorithm to reduce inapplicable options.
- Improved volume-measurement defaults and wording; fixed camera-group deletion, algorithm-path recognition, and result-routing issues.
- Improved packaging of the batch tools, optional pallet components, and backend autostart configuration.

### Later maintenance builds

The following changes belong to later 3.1.0 builds. They must not be assumed to exist in every early 3.1.0 installer.

- Provided independent parameter and calibration pages for each algorithm. Standard users enter the active algorithm page directly, and each algorithm retains its own extrinsic state.
- Organized slot settings by detection method, retained standard-user editing, saving, and sending, and reloaded device parameters when switching pages.
- Improved the interaction between volume measurement, placement-quality checks, and merging. Enabling placement quality also enables volume measurement; disabling placement quality preserves the volume-measurement state.
- Added coverage display to slot monitoring and improved status colors and multi-object results.
- Improved pallet P3D calibration and parameter pages, and isolated depalletizing hand-eye calibration from platform extrinsics.
- Introduced independent frontend, service, and algorithm version management. Later Windows packages adjusted algorithm dependencies and legacy-frontend packaging.
- Improved administrator checks for service shutdown while retaining standard-user access to restart.

### Upgrade notes

- Check the build date and component manifest as well as the version number; identical version numbers do not guarantee identical contents.
- The Windows frontend provides configuration and monitoring. It does not imply that every device-side inference algorithm is installed locally.
- Read back extrinsics after pallet calibration and validate coordinate directions and detection results on site.

<a id="aw3-301"></a>

## AW3 3.0.1

**Scope:** New UI and cumulative platform changes relative to the legacy UI baseline. **Public release date:** Not supplied.

### UI and device management

- Introduced AW3Viewer, organizing device lists, images, point clouds, parameters, and monitoring by algorithm scenario.
- Added camera display, filtering, and switching across multiple service instances, distinguishing connected devices from cached device states.
- Separated base-camera SDK parameters from algorithm parameters; virtual-camera display names are independent of internal identifiers.
- Improved stable camera binding, device replacement, deletion, and IP-address changes.
- Improved language switching, dialog layouts, point-cloud view retention, and display cleanup after device changes.

### Algorithm configuration and monitoring

- Added dedicated volume-measurement configuration and monitoring with up to five regions, per-object dimensions, display-unit switching, and point-cloud volume-estimation settings.
- Added multi-camera extrinsic calibration, error inspection, and fused point-cloud previews.
- Added RGB region editing, top-view annotation, batch generation, and 3D range adjustment for slots; improved saving, sending, status statistics, and occupancy display.
- Improved depalletizing product templates, regions, and extrinsics, with configuration synchronization, isolated multi-camera inference, and safety checks.

### Protocols and maintenance

- Added custom protocol rules and graphical configuration for TCP, UDP, HTTP, and Modbus integration and result-field mapping.
- Improved slot reporting, legacy TCP result queries, the depalletizing semicolon protocol, and the HNPS-A template.
- Fixed runtime updates to server-side result-forwarding options.
- Added batch parameter-management and upgrade tools with preview, backup, transmission/readback, and rollback of the current operation.
- Improved Windows component selection, runtime collection, initial language settings, and incremental upgrades.

### Upgrade notes

- Use matching frontend, service, and algorithm components. The listed capabilities do not imply that every installer contains all algorithm runtimes.
- Volume parameters use `regions`; results use `result.<region-id>.TM[]`. Raw dimensions are in mm and volumes in mm³.
- Check regions, extrinsics, result fields, and site protocol mappings after upgrading. Point-cloud real volume is an estimate.
- Newly integrated pallet-docking functionality belongs to AW3 3.1.0 and is not included in this entry.

<a id="legacy-ui"></a>

## Legacy UI

**Program:** AlgPlatformViewer. This entry records baseline capabilities for comparison with AW3Viewer; it does not assign an invented initial version number or publication date.

### Baseline capabilities

- Device connection, base-camera controls, algorithm enablement, parameters, slot detection, depalletizing, and result-log pages.
- Service connection, virtual-camera discovery, and target-camera selection for commissioning.
- RGB, result-image, and point-cloud display, with detection results and runtime logs.
- Reading, editing, and sending algorithm parameters, including dedicated slot and depalletizing configuration.
- Calibration and extrinsic configuration, with reasons and handling guidance for failed depalletizing region calibration.
- Selection of RGB image points to obtain corresponding 3D coordinates for on-site calibration.

### Migration notes

The legacy UI is organized around device commissioning and tool pages. AW3Viewer organizes configuration, calibration, and monitoring around algorithms. Identify the program by name as well as its displayed version.

Back up algorithm parameters, calibration extrinsics, and protocol settings before switching frontends, and reread device parameters after connection. Later maintenance of the legacy UI may contain additional features; those changes are not retrospectively assigned to its baseline.

## Related documentation

- [AW3 User Manual V0.1](../docs/aw3-application-algorithm-platform-user-manual-v0.1.pdf)
- [Application catalog](../../README.md)
