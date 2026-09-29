# Slot Monitoring

[Documentation Home](../README.md) / Slot Monitoring

StockSync detects storage-location occupancy, placement, alignment, and out-of-area conditions using MRDVS 3D vision. AW3 provides the frontend for configuration and monitoring; StockSync is delivered as a separate algorithm package.

| Status | Value |
| --- | --- |
| Frontend | AW3; install the frontend only |
| Algorithm package | StockSync `.tar.gz`; not yet published |
| AW3 backend | Do not install for this application |
| Latest recorded algorithm | [StockSync `3.1.1`](releases/README.md#stocksync-311); notes available |
| Current documentation | Camera-side user and deployment guide |

## Installation

| Required download | Install / use | Availability |
| --- | --- | --- |
| [AW3 installer](../aw3/README.md#installation) | Install the frontend only; do not install the AW3 backend | Not yet published |
| StockSync algorithm `.tar.gz` | Deploy the algorithm package following its device installation instructions | Not yet published |

Both downloads are required. The AW3 installer is maintained under AW3; this application's software Releases host the StockSync algorithm package only, without duplicating the AW3 installer. Compatible frontend, algorithm, and device versions must be specified with the published package.

## Start here

| Step | Resource |
| --- | --- |
| 1. Prepare the frontend and algorithm package | [Installation](#installation) |
| 2. Connect and configure the AW3 frontend | [AW3 User Manual](../aw3/docs/aw3-application-algorithm-platform-user-manual-v0.1.pdf) |
| 3. Review camera-side configuration and integration | [Slot Monitoring User Guide](docs/user-guide.md) |
| 4. Review algorithm changes | [Release Notes](releases/README.md) |

The camera-side guide uses **Storage Location Detection** where it matches the existing interface. Its screenshots and controls are not a substitute for AW3 frontend instructions.
