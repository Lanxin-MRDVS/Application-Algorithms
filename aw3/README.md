# AW3 Platform

[Documentation Home](../README.md) / AW3

AW3 is the target shared runtime and delivery platform for MRDVS 3D vision applications. It is intended to manage device connections, configuration, calibration, algorithm execution, result visualization, and task templates.

## Application plan

| Application | Current public delivery | Target delivery |
| --- | --- | --- |
| [Depalletizing](../depalletizing/README.md) | Standalone package `3.0.1` | AW3 |
| [Pallet Docking](../pallet-docking/README.md) | Standalone PalletPro `1.4.8_260828` | AW3 |
| [Volume Measurement](../volume-measurement/README.md) | No public package | AW3 |
| [Slot Monitoring](../slot-monitoring/README.md) | No public package | AW3 |

## Public release status

No verified public AW3 platform release is currently recorded in this repository. See the [AW3 release history](releases/README.md) for future platform releases.

The historical file `AW3-V3.0.1-20260624.zip` is managed as the current standalone Depalletizing package because its confirmed delivery is outside AW3. Its published filename and GitHub tag are preserved so existing links continue to work.

Future platform releases should use `aw3-v<major>.<minor>.<patch>` and include a manifest of the application versions delivered in the package.
