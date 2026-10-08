[Documentation Home](../README.md) / Depalletizing

<div align="center">

# Depalletizing

</div>

> **Before you update:** Check your installed package and algorithm versions. The current standalone delivery is separate from AW3; confirm that the guide applies to your deployment.

<details>
<summary><strong>Software history · standalone 3.0.1</strong></summary>

<a id="software-update-history"></a>

The public standalone package and the PalletEye algorithm record use independent version histories. Their shared `3.0.1` number does not establish that they contain the same changes.

| Component / version | Publication date | Release notes / download |
| --- | --- | --- |
| Legacy standalone `3.0.1` | 2026-07-03 | [Release notes](releases/README.md#legacy-standalone-301) · [Depalletizing Package (ZIP)](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/Depalletizing-Algorithm-V3.0.1/AW3-V3.0.1-20260624.zip) |

[All recorded changes](releases/README.md) also retain the separate PalletEye algorithm record; no matching public package was supplied with that record.

</details>

<details>
<summary><strong>Document history · Deployment Guide</strong></summary>

<a id="document-update-history"></a>

| Document | Version | Read |
| --- | --- | --- |
| Depalletizing Deployment Guide | Not supplied | [Markdown](docs/deployment-guide.md) |

Check the guide's delivery note before applying its instructions to the legacy standalone package.

</details>

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
| Deploy the application | [Deployment procedure](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/depalletizing/docs/deployment-guide.md#5-deployment-process) |
| Configure recognition and calibration | [Parameter configuration](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/depalletizing/docs/deployment-guide.md#4-parameter-configuration-part) |
| Integrate communication | [Communication protocol](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/depalletizing/docs/deployment-guide.md#6-communication-protocol) |
| Interpret results and error codes | [Visual inspection](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/depalletizing/docs/deployment-guide.md#7-visual-inspection) |
| Configure camera networks | [LxCameraViewer](../tools/lxcameraviewer/README.md) |

## Lifecycle

The published filename contains `AW3`, but the confirmed `3.0.1` delivery runs independently outside the AW3 platform lifecycle. The filename and tag remain unchanged for download compatibility. Future AW3 platform releases belong in the [AW3 release history](../aw3/releases/README.md); Depalletizing-specific patches remain in this application's [release history](releases/README.md) and must declare AW3 compatibility when applicable.
