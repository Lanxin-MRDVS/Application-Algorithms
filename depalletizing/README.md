# Depalletizing

[Documentation Home](../README.md) / Depalletizing

Depalletizing provides vision-guided soft-bag and carton unstacking. The current public `3.0.1` package is a standalone delivery; Depalletizing is planned to move to AW3.

| Status | Value |
| --- | --- |
| Current public delivery | Standalone application package |
| Latest public version | `3.0.1` (legacy standalone package) |
| Latest recorded algorithm | [PalletEye `3.0.1`](releases/README.md#palleteye-301); separate from the legacy package |
| Target delivery | AW3 |

## Start here

| Task | Resource |
| --- | --- |
| Download the current standalone package | [Depalletizing Package (ZIP)](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/Depalletizing-Algorithm-V3.0.1/AW3-V3.0.1-20260624.zip) |
| Review this application release | [3.0.1 release notes](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/depalletizing/releases/README.md#legacy-standalone-301) |
| Deploy the application | [Deployment procedure](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/depalletizing/docs/deployment-guide.md#5-deployment-process) |
| Configure recognition and calibration | [Parameter configuration](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/depalletizing/docs/deployment-guide.md#4-parameter-configuration-part) |
| Integrate communication | [Communication protocol](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/depalletizing/docs/deployment-guide.md#6-communication-protocol) |
| Interpret results and error codes | [Visual inspection](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/depalletizing/docs/deployment-guide.md#7-visual-inspection) |
| Configure camera networks | [LxCameraViewer](../tools/lxcameraviewer/README.md) |
| Review every published version | [Depalletizing release history](releases/README.md) |

## Lifecycle

The published filename contains `AW3`, but the confirmed `3.0.1` delivery runs independently outside the AW3 platform lifecycle. The filename and tag remain unchanged for download compatibility. Future AW3 platform releases belong in the [AW3 release history](../aw3/releases/README.md); Depalletizing-specific patches remain in this application's [release history](releases/README.md) and must declare AW3 compatibility when applicable.
