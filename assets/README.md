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

Keep the same style and colors when adding another `button-*.svg`, and use labels that describe its actual destination. The SDK version and ROS text in the reference badges are not PalletPro compatibility claims. Preserve SVG titles and meaningful image alt text in the referring page. Plain text navigation remains available alongside the image links.

The documentation homepage uses four algorithm badges: `button-pallet-docking.svg`, `button-obstacle-avoidance.svg`, `button-depalletizing.svg`, and `button-storage-location.svg`. All four use the **Algorithm** label and blue documentation color. Keep product names, document types, and download actions out of this primary classification; camera setup tools and software downloads have separate sections. Previously published badge files remain available to preserve existing image URLs.

`mrdvs_logo.png` is the existing MRDVS logo. Product screenshots belong in the relevant application's image folder, such as `PalletPro/images/`.
