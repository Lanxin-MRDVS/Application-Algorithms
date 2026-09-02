# Repository Structure

[Documentation Home](../README.md) / [Maintenance Guide](README.md) / Repository Structure

The root directory is intentionally limited to five content groups and three index files:

```text
Application-Algorithms/
├── applications/          # Algorithm applications
│   └── <application>/
│       ├── README.md      # Entry page, latest version, and key links
│       ├── docs/          # Documentation index plus technical and user guides
│       └── releases/      # Historical release index and version notes
├── platform/              # Shared application runtimes
│   └── aw3/
│       ├── README.md
│       └── releases/
├── tools/                 # Camera and deployment utilities
├── docs/                  # Repository maintenance standards
├── assets/                # Shared MRDVS brand and homepage graphics
├── README.md              # Public documentation homepage
├── RELEASES.md            # Central version and download index
└── SUMMARY.md             # GitBook-compatible navigation
```

## Naming rules

- Use lowercase kebab-case for folders: `pallet-docking`, `slot-monitoring`.
- Use stable, descriptive filenames: `deployment-guide.md`, `user-guide.md`, `protocol.md`.
- Use one release-note file per version: `releases/v1.2.3.md`.
- Keep the application name user-facing and keep software names inside its page. For example, the application is **Pallet Docking** and its current Windows tool is **PalletPro**.
- Put application-specific images in `docs/images/`; put shared visual assets in `/assets`.
- Do not commit `.exe`, `.zip`, firmware, models, customer configurations, logs, or calibration backups to the Git tree.

## Entry-page contract

Every application `README.md` must contain:

1. Application purpose and runtime.
2. Latest verified public package or an explicit “No public release yet” status.
3. Links to technical documentation.
4. A link to `releases/README.md`.
5. Compatibility or lifecycle notes when the application is moving to AW3.

## Link maintenance

When moving or adding a page, update:

1. The application entry page.
2. The application release index.
3. `/README.md` when the item is a primary entry or current download.
4. `/RELEASES.md` when a public package changes.
5. `/SUMMARY.md` for GitBook navigation.

Run the repository link check before publishing and preserve existing GitHub Release asset URLs.
