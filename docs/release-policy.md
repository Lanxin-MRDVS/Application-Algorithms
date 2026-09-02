# Release and Versioning Policy

[Documentation Home](../README.md) / [Maintenance Guide](README.md) / Release Policy

This policy separates the AW3 platform lifecycle from faster application updates while keeping every package traceable.

## 1. Release ownership

| Release type | Owner | When to use it | Example |
| --- | --- | --- | --- |
| **AW3 platform release** | AW3 | Runtime changes, major/minor platform delivery, shared services, or a coordinated application bundle. | `aw3-v3.1.0` |
| **Application release** | One application | Short-cycle fixes, algorithm tuning, or a feature package that does not require a new AW3 platform release. | `pallet-docking-v1.2.1` |
| **Tool release** | One standalone utility | Independent desktop or diagnostic software such as PalletPro. | `palletpro-v1.4.8-260828` |

Depalletizing, Pallet Docking, Volume Measurement, and Slot Monitoring use AW3 as their target runtime. Obstacle Avoidance remains a camera application until its verified packaging changes.

GitHub provides one repository-wide **Latest Release** rather than a separate latest marker for every application. Treat `/RELEASES.md` and each application's `releases/README.md` as the authoritative component-level indexes. Prefix every GitHub Release title with its platform or application scope, and never create an empty Release only to make an application appear in the repository sidebar.

## 2. Version rules

Use semantic versioning where the product exposes a three-part version:

- `MAJOR`: incompatible behavior, interface, configuration, or deployment changes.
- `MINOR`: backward-compatible features.
- `PATCH`: backward-compatible fixes and tuning.

A build identifier may follow the version when the delivered product already uses one, for example `1.4.8_260828`. Do not derive a release date or compatibility claim from a filename alone.

## 3. Required names

| Item | Format |
| --- | --- |
| AW3 tag | `aw3-v<major>.<minor>.<patch>` |
| Application tag | `<application>-v<major>.<minor>.<patch>` |
| Tool tag | `<tool>-v<version>` |
| AW3 release title | `AW3 v<version> · <primary scope>` |
| Application release title | `<Application> · v<version>` |
| Application-specific tool title | `<Application> · <Tool> v<version>` |
| Platform asset | `aw3-v<version>-<os>-<arch>.<ext>` |
| Application asset | `<application>-v<version>-for-aw3-<range>.<ext>` |
| Tool asset | `<tool>-v<version>-<os>-<arch>.<ext>` |
| Release-note file | `releases/v<version>.md` |

Keep the historical tags `Depalletizing-Algorithm-V3.0.1` and `PalletPro` unchanged so existing download URLs remain valid.

## 4. Required release metadata

Every published version must have a release note containing:

- Version and publication date.
- Release type and stability status.
- Compatible AW3 range for application packages.
- Supported operating systems, architectures, and camera or firmware requirements when verified.
- Summary, new features, improvements, and fixes.
- Breaking changes or an explicit statement that none are known.
- Upgrade steps and rollback steps.
- Known issues.
- Exact asset filenames, byte sizes, and SHA-256 checksums.
- Links to the applicable user, deployment, API, and protocol documentation.

Unknown information must be written as **Not verified** or **Not published**. Do not infer it.

## 5. Storage model

- Attach all installers, ZIP packages, firmware, and models to GitHub Releases or the official download service.
- Keep only Markdown release notes and small documentation assets in Git.
- Keep one immutable release-note file per version inside the owning platform, application, or tool folder.
- Keep an application-specific utility such as PalletPro under its owning application; reserve `/tools` for shared utilities such as LxCameraViewer.
- Keep `RELEASES.md` as the central index and each `releases/README.md` as the local history.
- Never replace an existing release asset in place. Publish a new version so users can reproduce and roll back deployments.

## 6. Publication workflow

1. Confirm the release owner: AW3, application, or tool.
2. Freeze the version, compatibility range, and asset filenames.
3. Create the version note from [the template](release-note-template.md).
4. Build and test the package using the approved release process.
5. Record file sizes and SHA-256 values.
6. Create the immutable Git tag and GitHub Release.
7. Upload assets and copy the final download URLs into the version note.
8. Update the local release index, `/RELEASES.md`, the product entry page, and the homepage latest-download area.
9. Verify links, rendering, downloads, and rollback instructions.
10. Preserve all previous release notes and assets.
