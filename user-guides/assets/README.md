# Shared Assets

[Documentation Home](../README.md) / Shared Assets

This directory contains repository-wide MRDVS brand and navigation graphics. Application screenshots belong under the relevant application's `docs/images/` directory.

## Brand

| File | Purpose |
| --- | --- |
| `mrdvs-logo-en.webp` | English MRDVS logo used on the documentation homepage. |
| `mrdvs-logo-cn.png` | Chinese MRDVS logo retained as a brand asset; not used on the documentation homepage. |

## Homepage navigation

The five application buttons and the AW3 platform button are equal-width SVG assets. Their colors stay within the blue-to-cyan MRDVS brand range derived from the English logo (`#1964FF` and `#15D1FF`).

| Application | SVG | Size |
| --- | --- | --- |
| AW3 | `button-aw3.svg` | 160 × 36 px |
| Depalletizing | `button-depalletizing.svg` | 160 × 36 px |
| Pallet Docking | `button-pallet-docking.svg` | 160 × 36 px |
| Volume Measurement | `button-volume-measurement.svg` | 160 × 36 px |
| Slot Monitoring | `button-slot-monitoring.svg` | 160 × 36 px |
| Obstacle Avoidance | `button-obstacle-avoidance.svg` | 160 × 36 px |

All buttons use white text, meaningful SVG titles, and meaningful image alt text in the referring page. The homepage also provides text links, so navigation does not rely on color alone.

## Product-page actions and diagrams

| File | Purpose |
| --- | --- |
| `button-download-palletpro-latest.svg` | Current PalletPro download. |
| `button-user-guide-large.svg` | Prominent user-guide navigation. |
| `aw3-application-model.svg` | Current and target application-delivery model. |

New shared assets should use short lowercase kebab-case names, the MRDVS palette, accessible titles, and source-controlled SVG where practical.

Do not place product screenshots here. For example, Pallet Docking screenshots are stored in `pallet-docking/docs/images/`.
