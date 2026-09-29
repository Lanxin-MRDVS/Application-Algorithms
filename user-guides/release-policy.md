# Release and Versioning Policy

[Documentation Home](../README.md) / [User Guides](README.md) / Release Policy

This policy defines package ownership and installation requirements while retaining earlier standalone releases.

## 1. Current and target delivery

| Application | Current public delivery | Target delivery |
| --- | --- | --- |
| Depalletizing | Standalone `3.0.1` package | AW3 |
| Pallet Docking | SmartDocking package pending; legacy PalletPro retained | AW3 frontend only + SmartDocking `.tar.gz`; no AW3 backend |
| Volume Measurement | Documentation `V0.1`; TorusMetric `2.0.1` notes available, public package not published | AW3 installer only; install frontend + backend |
| Slot Monitoring | StockSync notes available; no public package | AW3 frontend only + StockSync `.tar.gz`; no AW3 backend |
| Obstacle Avoidance | AW3 Obstacle Workstation `1.0.19`; V0.1 manual and white paper | Dedicated Obstacle Workstation host application |

The historical Depalletizing asset is named `AW3-V3.0.1-20260624.zip`, but its confirmed product ownership is the standalone Depalletizing lifecycle. Preserve the filename and published tag for compatibility.

## 2. Release ownership

| Release type | Owner | Use it for | Example |
| --- | --- | --- | --- |
| **AW3 platform release** | AW3 | Shared frontend installer and the backend used for Volume Measurement. | `aw3-v3.1.0` |
| **Application release** | One algorithm | Application algorithm installation packages, including StockSync and SmartDocking `.tar.gz`, or application-specific updates. | `depalletizing-v3.0.2` |
| **Application host software** | Owning algorithm | Independent desktop software such as PalletPro or Obstacle Workstation. | `palletpro-v1.4.9` |
| **Shared tool release** | Tool | Camera setup, diagnostic, or integration utilities used by multiple applications. | `lxcameraviewer-v2.5.0` |

AW3 is the shared frontend for Volume Measurement, Slot Monitoring, and Pallet Docking. Volume Measurement additionally installs the AW3 backend and needs no separate algorithm package. Slot Monitoring and Pallet Docking do not install the AW3 backend: each requires its own algorithm `.tar.gz`. These are application installation packages, not necessarily patches. Depalletizing remains a target AW3 application; its existing standalone delivery is unchanged. Obstacle Avoidance follows its dedicated host-application lifecycle.

Publish the AW3 installer once under an AW3 software Release. Publish StockSync and SmartDocking algorithm archives under their respective application software Releases, without copying the AW3 installer into them. Product folders hold documentation and package links, not binary copies. Preserve legacy PalletPro assets in their historical Release.

For Volume Measurement, the product-page software history records both formal TorusMetric versions and standalone updates in one table. Formal versions are owned by the AW3 release that contains them; installer links point to that AW3 Release. Algorithm-specific changes remain in the application's single `releases/README.md`, with a link to the corresponding AW3 version when verified. Standalone update packages belong to software Release assets, and their notes are sections in the same application file. Every previous version row must be retained.

GitHub provides one repository-wide **Latest Release**, so component-level latest versions are defined by `latest-downloads/README.md` and the owning product page. The homepage **Latest software** table shows the latest AW3 formal release, the latest separately distributed algorithm installation package or update for each application, and the latest Obstacle Avoidance host application. It is a current-release view, not a historical index. Prefix every GitHub Release title with its product scope, and never publish an empty Release only to change the sidebar.

## 3. Version and naming rules

Use semantic versioning where the product exposes a three-part version. A build identifier may follow the version when the delivered product already uses one, for example `1.4.8_260828`. Do not infer a release date or compatibility claim from a filename alone.

| Item | Format |
| --- | --- |
| AW3 tag | `aw3-v<major>.<minor>.<patch>` |
| Application tag | `<application>-v<major>.<minor>.<patch>` |
| Host software tag | `<software>-v<version>` |
| Shared tool tag | `<tool>-v<version>` |
| Release-note file | `<product>/releases/README.md` (one file, all versions) |

Keep the historical tags `Depalletizing-Algorithm-V3.0.1` and `PalletPro` unchanged so existing download URLs remain valid.

### Product-page release status

Each application product page uses the same compact release-status structure:

1. **Latest documentation:** show the current document version, publication date, applicable formal software version, and links to the latest user manual and white paper when available.
2. **Latest formal software:** show one latest formal application version and its delivery relationship: bundled AW3 version for Volume Measurement, or compatible AW3 frontend plus separate algorithm package for Slot Monitoring and Pallet Docking. Mark unpublished packages explicitly.
3. **Applicable standalone updates:** show active, non-superseded updates that explicitly reference the latest formal software version and its compatible AW3 version, or `Not published`.

The status card has strict display limits:

- **Latest documentation:** at most two links, consisting of one current User Manual and one current White Paper.
- **Latest formal software:** exactly one latest published formal version. Before the first formal release, show one next planned version instead.
- **Applicable standalone updates:** up to three active, non-superseded updates for the latest formal version. If more than three apply, show the three newest and route users to the complete history. If none applies, show `Not published`.

Do not show earlier versions in the status card. Provide one in-page link to the complete software update history at the bottom of the product page, which retains every formal version and standalone update. Keep detailed changes, checksums, compatibility, upgrade instructions, and rollback instructions in the owning product's single `releases/README.md`, organized into retained version sections. Keep the document update history at the bottom of the product page and retain earlier document files in `docs/`.

Formal software is the application baseline. Each formal version records its delivery relationship: the containing AW3 release for Volume Measurement, or the compatible AW3 frontend plus its separately delivered algorithm package for Slot Monitoring and Pallet Docking. Each standalone update records its own version, its formal-version baseline, its compatible AW3 version, whether it remains active, and any update it supersedes. Each document version records the formal software versions, standalone updates, and AW3 versions to which it applies. Use `TBC` until an identifier is assigned and verified; never infer a relationship from an asset filename.

## 4. Required release metadata

Every published version must include its version and publication date, release type, delivery status, compatibility, supported environment when verified, summary, changes and fixes, upgrade and rollback guidance, known issues, asset filenames, file sizes, SHA-256 checksums, and applicable documentation links. Write **Not verified** or **Not published** for unknown information; never infer it.

## 5. Storage model

- Attach installers, archives, firmware, and models to GitHub Releases or the official download service.
- Keep Markdown release notes, public manuals, white papers, and reasonably sized documentation assets in Git.
- Keep exactly one Release Notes file per AW3 platform or algorithm: `<product>/releases/README.md`. Record all versions in that file, newest first; retain legacy versions and identify their component names explicitly. Shared tools follow the same pattern when notes are maintained here.
- Use stable component-and-version anchors. Product pages summarize availability and link to those sections; they do not maintain a second detailed changelog. GitHub Release descriptions contain a concise software summary and a link to the canonical section. Do not upload duplicate release-note attachments.
- Treat frontend, backend, and algorithm versions independently. A notes compilation date is not a software publication date. Notes alone do not establish a downloadable package, a formal bundle, compatibility, or test results.
- Keep application-specific software under its application; reserve `tools/` for shared utilities such as LxCameraViewer.
- Keep the current package index in `latest-downloads/README.md`; retain `RELEASES.md` as a compatibility entry that routes users to product-owned histories.
- Never replace an existing software binary in place. Publish a new software version so deployments remain reproducible and reversible. Preserve historical tags and binary download URLs. When consolidating redundant note attachments, repair their links and refresh any affected checksum manifest without changing the software binaries.

## 6. Publication workflow

### Document reading and downloads

The Releases list contains software publications only. Never create a documentation-only Release. Manuals and guides remain owned by their product, and document revisions do not create software versions.

All document entry links on repository pages and software Release descriptions open the GitHub preview of the owning Markdown or PDF file. Markdown guides display their images and support links to individual sections. Users can use GitHub's file download controls when they need a local copy. Word source files are not published.

Software installers, software ZIP packages, and checksum files retain direct download links. Existing documentation attachments may remain with their software releases as optional downloads, but they are not the default document-reading entry point. Do not generate document-only ZIP files to force a download.

When reorganizing documentation, update the homepage, product pages, guide index, release descriptions, and navigation. Verify preview links, section anchors, and image URLs. Preserve software installers, version numbers, historical tags, and release dates. Link repairs must not change technical claims.

### Release presentation

Use the existing product title, centered consistently. Show the current release's existing delivery information, changes, and document links clearly; fold long installation and verification details where useful. Preserve existing wording and important limitations. Do not invent features, compatibility, test results, dates, or new documentation sections solely to fill a layout. Keep the latest published software marked as Latest; product-specific latest versions remain on the homepage and product pages.

### Software publication

1. Confirm the owner: AW3, application, application host software, or shared tool.
2. Freeze the version, compatibility, and asset filenames.
3. Add a version section to the owning `releases/README.md` using [the template](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/user-guides/release-note-template.md).
4. Build and test the package through the approved release process.
5. Record file sizes and SHA-256 values.
6. Create the immutable Git tag and GitHub Release.
7. Upload assets and copy the final URLs into the version note.
8. Update the canonical Release Notes file, `latest-downloads/README.md`, the product page, the homepage, and `SUMMARY.md`.
9. Verify links, rendering, downloads, compatibility, and rollback instructions.
10. Preserve every previous version section and software asset.
