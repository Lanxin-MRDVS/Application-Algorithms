# Release and Versioning Policy

[Documentation Home](../README.md) / [User Guides](README.md) / Release Policy

This policy keeps current standalone products available while establishing clear ownership for future AW3 and host-application releases.

## 1. Current and target delivery

| Application | Current public delivery | Target delivery |
| --- | --- | --- |
| Depalletizing | Standalone `3.0.1` package | AW3 |
| Pallet Docking | Standalone PalletPro `1.4.8_260828` host application | AW3 |
| Volume Measurement | No public package | AW3 |
| Slot Monitoring | No public package | AW3 |
| Obstacle Avoidance | No public package; current camera-side guide | Dedicated host application |

The historical Depalletizing asset is named `AW3-V3.0.1-20260624.zip`, but its confirmed product ownership is the standalone Depalletizing lifecycle. Preserve the filename and published tag for compatibility.

## 2. Release ownership

| Release type | Owner | Use it for | Example |
| --- | --- | --- | --- |
| **AW3 platform release** | AW3 | Future major shared runtime delivery or a coordinated application bundle. | `aw3-v3.1.0` |
| **Application release** | One algorithm | Standalone delivery or a short-cycle algorithm fix or feature package. | `depalletizing-v3.0.2` |
| **Application host software** | Owning algorithm | Independent desktop software such as PalletPro or the planned Obstacle Avoidance host application. | `palletpro-v1.4.9` |
| **Shared tool release** | Tool | Camera setup, diagnostic, or integration utilities used by multiple applications. | `lxcameraviewer-v2.5.0` |

Future Depalletizing, Pallet Docking, Volume Measurement, and Slot Monitoring use AW3 as their target delivery. Obstacle Avoidance follows its dedicated host-application lifecycle.

GitHub provides one repository-wide **Latest Release**, so component-level latest versions are defined by `latest-downloads/README.md` and each application's `releases/README.md`. Prefix every GitHub Release title with its product scope, and never publish an empty Release only to change the sidebar.

## 3. Version and naming rules

Use semantic versioning where the product exposes a three-part version. A build identifier may follow the version when the delivered product already uses one, for example `1.4.8_260828`. Do not infer a release date or compatibility claim from a filename alone.

| Item | Format |
| --- | --- |
| AW3 tag | `aw3-v<major>.<minor>.<patch>` |
| Application tag | `<application>-v<major>.<minor>.<patch>` |
| Host software tag | `<software>-v<version>` |
| Shared tool tag | `<tool>-v<version>` |
| Release-note file | `releases/v<version>.md` |

Keep the historical tags `Depalletizing-Algorithm-V3.0.1` and `PalletPro` unchanged so existing download URLs remain valid.

## 4. Required release metadata

Every published version must include its version and publication date, release type, delivery status, compatibility, supported environment when verified, summary, changes and fixes, upgrade and rollback guidance, known issues, asset filenames, file sizes, SHA-256 checksums, and applicable documentation links. Write **Not verified** or **Not published** for unknown information; never infer it.

## 5. Storage model

- Attach installers, archives, firmware, and models to GitHub Releases or the official download service.
- Keep Markdown release notes and small documentation assets in Git.
- Keep one immutable release-note file per version inside the owning AW3, application, or tool folder.
- Keep application-specific software under its application; reserve `tools/` for shared utilities such as LxCameraViewer.
- Keep the current package index in `latest-downloads/README.md`; retain `RELEASES.md` as a compatibility entry that routes users to product-owned histories.
- Never replace an existing release asset in place. Publish a new version so deployments remain reproducible and reversible.

## 6. Publication workflow

1. Confirm the owner: AW3, application, application host software, or shared tool.
2. Freeze the version, compatibility, and asset filenames.
3. Create the version note from [the template](release-note-template.md).
4. Build and test the package through the approved release process.
5. Record file sizes and SHA-256 values.
6. Create the immutable Git tag and GitHub Release.
7. Upload assets and copy the final URLs into the version note.
8. Update the owning release index, `latest-downloads/README.md`, the product page, the homepage, and `SUMMARY.md`.
9. Verify links, rendering, downloads, compatibility, and rollback instructions.
10. Preserve every previous release note and asset.
