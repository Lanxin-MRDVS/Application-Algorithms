# Slot Monitoring Release Notes

[Documentation Home](../../README.md) / [Slot Monitoring](../README.md) / Release Notes

This is the single release-note file for StockSync. The supplied notes were compiled on **2026-09-22**; this is not a software publication date. The 3.1.1 full device update is published below. Package build and publication dates are recorded separately.

| Version | Scope | Public release date | Package |
| --- | --- | --- | --- |
| [3.1.1](#stocksync-311) | Full RK3588 device update; build 2026-09-24 | 2026-09-29 | [Algorithm tar.gz](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/stocksync-v3.1.1/AW3_camera_SDK_stocksync_full_update_rk3588_260924_3.1.1.tar.gz) |

### Installation and package ownership

Use the [AW3 installer](../../aw3/README.md#installation) for the frontend only, plus the StockSync algorithm `.tar.gz`. Do not install the AW3 backend. StockSync software Releases own the algorithm package; the AW3 installer remains under AW3.

<a id="stocksync-311"></a>

## StockSync 3.1.1

### Published package

| Item | Value |
| --- | --- |
| Publication date | 2026-09-29 |
| Package build date | 2026-09-24 |
| Algorithm version | StockSync `3.1.1`, confirmed by the packaged component record |
| Target | RK3588 / Linux ARM64 |
| Package | [AW3_camera_SDK_stocksync_full_update_rk3588_260924_3.1.1.tar.gz](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/stocksync-v3.1.1/AW3_camera_SDK_stocksync_full_update_rk3588_260924_3.1.1.tar.gz) |
| Size | 173,136,699 bytes |

Use the AW3 PC frontend only, with no AW3 PC backend. The full device update is deployed on the matching RK3588 device / center. The `.bin` source is a valid gzip-compressed tar archive; only its published suffix changed to `.tar.gz`, without changing the contents.

<details>
<summary><strong>SHA-256</strong></summary>

```text
9ab80e42b3fee25cf17d2cf45a3dbffcea7fd5904612d530eb6782ec99cc5aae
```

[SHA256SUMS.txt](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/stocksync-v3.1.1/SHA256SUMS.txt)

</details>

The following change record is retained from the supplied 2026-09-22 release notes.

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
- Manage frontend and algorithm versions separately. Use the AW3 frontend separately; a hardware-tested compatibility range is not supplied by the package metadata.

### Documentation

- [StockSync User Manual V0.1](../docs/stocksync-user-manual-v0.1.pdf)
- [StockSync White Paper V0.1](../docs/stocksync-white-paper-v0.1.pdf)
- [Legacy camera-side guide](../docs/user-guide.md)
