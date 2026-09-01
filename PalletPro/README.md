<p align="center"><img src="../assets/mrdvs-logo-en.webp" alt="MRDVS Mobile Robot Vision Expert" width="300"></p>

[Documentation Home](../README.md) / PalletPro

# PalletPro

**Pallet Recognition & Docking · Eagle-M Series Cameras**

Configure cameras, teach pallet positions, and calibrate docking with the PalletPro Windows application.

<p align="center">
  <a href="user-guide.md"><img src="../assets/button-user-guide.svg" alt="Read the PalletPro user guide" height="20"></a>
  <a href="https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe"><img src="../assets/button-download-installer.svg" alt="Download PalletPro 1.4.8_260828 for Windows" height="20"></a>
  <a href="release-notes.md"><img src="../assets/button-release-notes.svg" alt="Read PalletPro release notes" height="20"></a>
</p>

**Current build:** `1.4.8_260828` · **Platform:** Windows

## Get started

| Step | Where to go |
| --- | --- |
| **1. Install PalletPro** | [Download the installer and verify its checksum](#software-download). |
| **2. Set up and calibrate** | Follow the [camera setup and calibration workflow](user-guide.md#4-initial-setup-and-calibration-going-through). |
| **3. Integrate docking results** | Read the [API, UDP, TCP, and CAN communication guide](user-guide.md#5-data-communication-methods). |

## Software download

| Item | Details |
| --- | --- |
| Application version | 1.4.8 |
| Installer product version | `1.4.8_260828` |
| Installer | [PalletPro-install-v1.4.8_260828.exe](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe) |
| File size | 118,296,332 bytes (112.82 MiB) |
| Release page | [PalletPro releases and assets](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/tag/PalletPro) |
| Earlier package | [PalletPro_1.4.8.zip](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro_1.4.8.zip) |

See the [1.4.8_260828 release notes](release-notes.md) for English-localization and terminology improvements, the known limitation, and upgrade guidance. Back up settings and calibration data before updating.

<details>
<summary>Verify your download — SHA-256 and PowerShell command</summary>

**SHA-256**

```text
c1bcc40900eb0c3f282c5657a7c3d06b69629483ec1674f4da347a295485dc3c
```

To verify a downloaded installer in PowerShell:

```powershell
Get-FileHash -LiteralPath '.\PalletPro-install-v1.4.8_260828.exe' -Algorithm SHA256
```

The installer product version above was read from the supplied executable's Windows version metadata. The installer has not been run as part of this documentation update. The earlier detailed localization record dated 2026-08-21 remains available through the historical reference in the release notes.

</details>

## Documentation

| Resource | Purpose |
| --- | --- |
| [User Guide](user-guide.md) | Camera installation, application interfaces, parameter configuration, near/far teaching, calibration verification, and API/UDP/TCP/CAN communication. |
| [Release Notes](release-notes.md) | English and Chinese release notes for 1.4.8_260828, including changes, terminology updates, the known limitation, and upgrade guidance. |
| [LxCameraViewer User Guide](../LxCameraViewer/README.md) | Camera connection, network configuration, parameter settings, and image/point-cloud inspection. |
| [CameraSDK](https://github.com/Lanxin-MRDVS/CameraSDK) | Camera SDK and LxCameraViewer resources. The user guide explains when to use LxCameraViewer for camera configuration and when to switch to PalletPro. |

The storage-location detection and depalletizing manuals in this repository describe separate application workflows; they are not PalletPro installation or release notes.

<details>
<summary>For maintainers: updating PalletPro content</summary>

## Maintaining PalletPro content

1. **Distribute installers through GitHub Releases.** Keep executables out of the Git file history. Preserve earlier assets and their download URLs when adding a new build.
2. **Use this page as the download index.** Update the installer filename, product version, byte size, and SHA-256 together after verifying the uploaded asset.
3. **Keep user instructions in the user guide.** Store screenshots in `images/` with short, descriptive English filenames; see the [screenshot index](images/README.md). Update affected procedures, screenshots, and UI labels when behavior changes, and record which application/embedded-algorithm versions were checked.
4. **Keep release history in `release-notes.md`.** Add a dated section for each confirmed release or build, describing changes, compatibility, known limitations, and its installer. Preserve previous entries and do not infer changes from a filename.
5. **Keep navigation connected.** Check the PalletPro links on the [documentation homepage](../README.md), in the [GitBook navigation](../SUMMARY.md), and on the GitHub release page whenever pages are added or renamed.
6. **Use versioned tags for future releases.** A tag such as `PalletPro-v<version>-<build>` keeps each package and its notes traceable. Keep the existing `PalletPro` release available so current download links continue to work.

## Documentation items to verify

- Figures 4–14 use refreshed English-interface screenshots. Other screenshots and remaining UI labels still need to be reconciled with the terminology recorded in the 1.4.8 update note.
- The far-end teaching distances differ between the interface explanation and the deployment procedure (sections 3.3.1 and 4.6). Confirm the intended conditions with the algorithm owner before changing either procedure.
- Confirm the supported Windows versions, matching camera firmware/embedded-algorithm versions, and upgrade/rollback steps before adding compatibility claims for build `260828`.

</details>

---

[Documentation Home](../README.md) · [User Guide](user-guide.md) · [Release Notes](release-notes.md) · [Release Page](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/tag/PalletPro)
