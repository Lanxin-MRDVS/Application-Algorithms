# Shared brand assets

Documentation and download actions use the compact, two-part Shields badge style from the supplied MRDVS brand references: [SDK badge](https://img.shields.io/badge/SDK-2.4.60.260126-2563EB) and [robotics badge](https://img.shields.io/badge/robotics-ROS%20%7C%20ROS2-0891B2). The homepage algorithm navigation uses larger, flat navigation bars based on colors sampled from the English MRDVS logo.

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

The documentation homepage uses four equal-size algorithm navigation bars. Each is **194 × 38px**, uses centered **15px bold** text, and appears in one row on a standard GitHub README. The labels are intentionally concise so the row remains readable; narrow screens can wrap naturally.

| Algorithm application | Navigation label | SVG file | MRDVS color |
| --- | --- | --- | --- |
| Pallet Recognition & Docking | Pallet Docking | `button-pallet-docking.svg` | Primary blue `#1964FF` |
| Obstacle Avoidance | Obstacle Avoidance | `button-obstacle-avoidance.svg` | Cyan `#15D1FF` |
| Depalletizing | Depalletizing | `button-depalletizing.svg` | Deep blue `#2057CC` |
| Storage Location Detection | Storage Detection | `button-storage-location.svg` | Light cyan `#5DE8FF` |

The two blue bars use white text; the two cyan bars use the logo's dark gray `#343132` text for contrast. Navigation therefore remains understandable without relying on color alone. Keep product names, document types, and download actions out of this primary classification; camera setup tools and software downloads have separate sections. Previously published badge files remain available to preserve existing image URLs.

`mrdvs-logo-en.webp` is the English logo used in repository README pages. Product screenshots belong in the relevant application's image folder, such as `PalletPro/images/`.
