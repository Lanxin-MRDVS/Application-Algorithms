# Shared brand assets

The navigation links use the compact Shields badge style from the supplied MRDVS brand references: [SDK badge](https://img.shields.io/badge/SDK-2.4.60.260126-2563EB) and [robotics badge](https://img.shields.io/badge/robotics-ROS%20%7C%20ROS2-0891B2).

The SVG files are stored in this repository and linked from the documentation home and PalletPro overview. GitHub handles navigation without custom JavaScript or page CSS; rendering the pages does not require a live Shields image request.

| Badge property | Value |
| --- | --- |
| Style | Shields default `flat` |
| Label background | `#555555` |
| Documentation content background | `#2563EB` |
| Download content background | `#0891B2` |
| Text | White |
| Height | `20px` |
| Corner radius | `3px` |
| Font family | Verdana, Geneva, DejaVu Sans, sans-serif |

Keep the same badge style when adding another `button-*.svg`, and use labels that describe its actual destination. Use the general colors above for document and download actions, and the category colors below for the primary algorithm navigation. The SDK version and ROS text in the reference badges are not PalletPro compatibility claims. Preserve SVG titles and meaningful image alt text in the referring page. Plain text navigation remains available alongside the image links.

The documentation homepage uses four equal-size, single-label algorithm badges. Each is **190 × 20px**, uses the original Shields-style type and shading, and appears in one row on a standard GitHub README. The labels are intentionally concise and do not repeat the word “Algorithm”; narrow screens can wrap naturally.

| Algorithm application | Navigation label | SVG file | Category color |
| --- | --- | --- | --- |
| Pallet Recognition & Docking | Pallet Docking | `button-pallet-docking.svg` | Blue `#2563EB` |
| Obstacle Avoidance | Obstacle Avoidance | `button-obstacle-avoidance.svg` | Deep cyan `#0E7490` |
| Depalletizing | Depalletizing | `button-depalletizing.svg` | Violet `#7C3AED` |
| Storage Location Detection | Storage Detection | `button-storage-location.svg` | Green `#15803D` |

All four badges use white text and retain meaningful alt text in the homepage links. Navigation therefore remains understandable without relying on color alone. Keep product names, document types, and download actions out of this primary classification; camera setup tools and software downloads have separate sections. Previously published badge files remain available to preserve existing image URLs.

`mrdvs-logo-en.webp` is the English logo used in repository README pages. Product screenshots belong in the relevant application's image folder, such as `PalletPro/images/`.
