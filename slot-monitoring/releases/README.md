# Slot Monitoring Release Notes

[Documentation Home](../../README.md) / [Slot Monitoring](../README.md) / Release Notes

This is the single release-note file for StockSync. The supplied notes were compiled on **2026-09-22**; this is not a software publication date. No public StockSync installation or update package is currently hosted in this repository.

| Version | Scope | Public release date | Package |
| --- | --- | --- | --- |
| [3.1.1](#stocksync-311) | Volume-box orientation fix; companion changes identified separately | Not supplied | Not published |

<a id="stocksync-311"></a>

## StockSync 3.1.1

### Algorithm fix

Fixed volume boxes in the result point cloud not matching the measured goods' orientation. The box now rotates with the measured angle.

### Companion UI and existing capabilities

- Supports 2D and 3D slot configuration and region editing, with status, occupancy, coverage, and multi-object result displays.
- Supports volume measurement, placement-quality checks, and volume merging. Placement-quality checks depend on volume measurement.
- Retains standard-user access to read, edit, save, and send slot configuration.
- Supports optional image saving when RGB changes. Using slot monitoring does not automatically enable this option.

These are companion-version capabilities, not all newly introduced algorithm features in 3.1.1.

### Companion MDS backend update

The following changes belong to MDS camera and service update packages. They are **not included in an update that replaces only the StockSync algorithm library**.

- Improved handling of repeated intrinsic-parameter notifications and duplicate frame metadata that could stop image updates.
- Improved RGB display when RGB/depth frame numbers or timestamps do not match.
- Adjusted MDS mode-setting behavior and removed an extra operation that could incorrectly revert the mode.
- Added separate MDS logs for parameter settings, frame acquisition, and pairing diagnostics.

Companion test records still identify occasional missing frames. This note does not claim that the issue is fully resolved.

### Upgrade notes

- Use the StockSync-specific update when only the volume-box orientation fix is needed. Use the corresponding camera/service/slot combination package when MDS updates are required.
- Check slot regions, calibration extrinsics, and volume-box orientation after upgrading.
- Manage frontend and algorithm versions separately. A verified AW3 compatibility range and public download URLs were not supplied.

### Documentation

- [Slot Monitoring User Guide](../docs/user-guide.md)
