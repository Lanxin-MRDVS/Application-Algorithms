# Release Note Section Template

[Documentation Home](../README.md) / Release Notes

> Add the section below to the owning product's existing `releases/README.md`, newest first. Do not create a separate version file or upload a duplicate note attachment. Keep earlier version sections. Replace placeholders with confirmed information; mark unknown dates or compatibility explicitly. Notes-only records must not imply that software is available.

<a id="component-version"></a>

## <Component> <Version>

Use a stable component-and-version anchor, for example `stocksync-311`. A compilation date is separate from the software publication date.

| Item | Details |
| --- | --- |
| Product / application | `<name>` |
| Version | `<version>` |
| Publication date | `YYYY-MM-DD` / `Not supplied` |
| Package availability | `<verified release link>` / `Not published` |
| Release type | `AW3 platform` / `Application package` / `Application host software` / `Shared tool` |
| Stability | `Stable` / `Pre-release` / `Hotfix` |
| Formal software baseline | `<version>` / `This version` / `Not applicable` / `TBC` |
| Delivered with / compatible AW3 | `<version or range>` / `Not applicable` / `Not verified` / `TBC` |
| Supersedes | `<standalone update versions>` / `None` / `Not applicable` |
| Applicable documentation | `<document versions and links>` / `Not published` |
| Supported OS / architecture | `<verified platforms>` |
| Camera / firmware requirements | `<verified requirements>` |

### Overview

Describe the user-visible purpose and scope of this version.

### New features

- List verified new capabilities.

### Improvements

- List verified behavior or performance improvements.

### Fixes

- List corrected defects and their operational impact.

### Compatibility and breaking changes

State configuration, API, protocol, model, firmware, and data-format compatibility. Write **No known breaking changes** only after verification.

### Upgrade procedure

1. Back up configurations, calibration data, and the previous package.
2. List the approved upgrade steps.
3. List the required post-upgrade checks.

### Rollback procedure

1. State how to restore the previous package and configuration.
2. State any data migration that cannot be reversed.

### Known issues

- List known limitations, or write **None documented** when confirmed.

### Downloads and verification

| Asset | Size | SHA-256 | Download |
| --- | ---: | --- | --- |
| `<filename>` | `<bytes>` | `<sha256>` | `<release asset URL>` |

### Documentation

- User or deployment guide: `<relative path to the owning application guide>`
- Product overview: `../README.md`
- [Latest downloads](https://github.com/Lanxin-MRDVS/Application-Algorithms/blob/main/latest-downloads/README.md)
