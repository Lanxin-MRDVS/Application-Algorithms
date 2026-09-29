# Repository Structure

[Documentation Home](../README.md) / [User Guides](README.md) / Repository Structure

The repository root uses exactly nine content folders so developers can understand the product structure directly from the GitHub file list:

```text
Application-Algorithms/
├── depalletizing/          # Application overview, current guide, and releases
├── pallet-docking/         # Application overview, current guide, and releases
├── volume-measurement/     # Application overview, current guide, and releases
├── slot-monitoring/        # Application overview, current guide, and releases
├── obstacle-avoidance/     # Application overview, current guide, and releases
├── aw3/                    # AW3 platform overview and major release history
├── tools/                  # Shared camera and integration tools
├── user-guides/            # Latest-guide hub, standards, and shared visuals
└── latest-downloads/       # Current verified package index
```

Root Markdown files provide the homepage, compatibility release index, and GitBook-compatible navigation.

## Application folder contract

Every application folder must contain:

```text
<application>/
├── README.md       # Purpose, delivery status, latest verified package, and key links
├── docs/           # Current technical or user guide
└── releases/       # One README.md containing all release-note version sections
```

## Naming and storage rules

- Use lowercase kebab-case for folders, such as `pallet-docking` and `slot-monitoring`.
- Use stable filenames such as `deployment-guide.md`, `user-guide.md`, and `protocol.md`.
- Use one Release Notes file per product: `releases/README.md`. Append each version as a section, newest first, and retain earlier sections. Use component-specific anchors when different components share a version number.
- Keep application-specific screenshots in `<application>/docs/images/` and shared visual assets in `user-guides/assets/`.
- Keep versioned public manuals and white papers in the owning application's `docs/` folder when their file sizes are suitable for Git. Use lowercase, descriptive filenames.
- Keep only the current package index in `latest-downloads/`; keep all historical version records under the owning product's `releases/` folder.
- Attach software installers, software ZIP packages, firmware, models, and other application binaries to software GitHub Releases. Do not commit them to the Git tree. Document links open Markdown or PDF previews; do not add document-only ZIP downloads.
- Do not commit customer configurations, logs, credentials, or calibration backups.

## Link maintenance

When publishing or moving content, update the application page, its release index, the root homepage, `latest-downloads/README.md` when the current package changes, and `SUMMARY.md`. Run the repository link check before publishing and preserve existing GitHub Release asset URLs.
