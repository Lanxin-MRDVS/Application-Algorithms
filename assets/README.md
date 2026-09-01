# Shared brand assets

The navigation links use the compact, two-part Shields badge style from the supplied MRDVS brand references: [SDK badge](https://img.shields.io/badge/SDK-2.4.60.260126-2563EB) and [robotics badge](https://img.shields.io/badge/robotics-ROS%20%7C%20ROS2-0891B2).

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

The documentation homepage uses four equal-size algorithm badges. Each is **248 × 20px**, with a **63px** gray label area and a **185px** category area. Keep the original 11px text size and text proportions; extend the background and center the text instead of stretching the image. Two equal-width badges per row align both columns on desktop, while narrow screens can wrap naturally.

| Algorithm application | Badge file | Category color |
| --- | --- | --- |
| Pallet Recognition & Docking | `button-pallet-docking.svg` | Blue `#2563EB` |
| Obstacle Avoidance | `button-obstacle-avoidance.svg` | Deep cyan `#0E7490` |
| Depalletizing | `button-depalletizing.svg` | Violet `#7C3AED` |
| Storage Location Detection | `button-storage-location.svg` | Green `#15803D` |

All four use the **Algorithm** label and keep their written category names, so navigation does not depend on color alone. Each category color provides at least 4.5:1 contrast with white text. Keep product names, document types, and download actions out of this primary classification; camera setup tools and software downloads have separate sections. Previously published badge files remain available to preserve existing image URLs.

`mrdvs-logo-en.webp` is the English logo used in repository README pages. Product screenshots belong in the relevant application's image folder, such as `PalletPro/images/`.
