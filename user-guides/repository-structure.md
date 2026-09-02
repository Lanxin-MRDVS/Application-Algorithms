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
└── releases/       # Local release index and one immutable note per version
```

## Naming and storage rules

- Use lowercase kebab-case for folders, such as `pallet-docking` and `slot-monitoring`.
- Use stable filenames such as `deployment-guide.md`, `user-guide.md`, and `protocol.md`.
- Use one release-note file per version, such as `releases/v1.2.3.md`.
- Keep application-specific screenshots in `<application>/docs/images/` and shared visual assets in `user-guides/assets/`.
- Keep only the current package index in `latest-downloads/`; keep all historical version records under the owning product's `releases/` folder.
- Attach `.exe`, `.zip`, firmware, models, and other binaries to GitHub Releases. Do not commit them to the Git tree.
- Do not commit customer configurations, logs, credentials, or calibration backups.

## Link maintenance

When publishing or moving content, update the application page, its release index, the root homepage, `latest-downloads/README.md` when the current package changes, and `SUMMARY.md`. Run the repository link check before publishing and preserve existing GitHub Release asset URLs.
