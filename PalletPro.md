# PalletPro: Pallet Recognition and Docking

PalletPro is the Windows application used to configure and calibrate pallet recognition and docking with MRDVS Eagle-M series cameras. Start here for software downloads, deployment instructions, and update notes.

## Software download

| Item | Details |
| --- | --- |
| Application version | 1.4.8 |
| Installer product version | `1.4.8_260828` |
| Installer | [PalletPro-install-v1.4.8_260828.exe](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro-install-v1.4.8_260828.exe) |
| File size | 118,296,332 bytes (112.82 MiB) |
| Release page | [PalletPro releases and assets](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/tag/PalletPro) |
| Earlier package | [PalletPro_1.4.8.zip](https://github.com/Lanxin-MRDVS/Application-Algorithms/releases/download/PalletPro/PalletPro_1.4.8.zip) |

The installer product version above was read from the supplied executable's Windows version metadata. See the [1.4.8_260828 release notes](PalletProUpdateNote.md) for the documented English-localization and terminology improvements, known limitation, and upgrade guidance. The earlier detailed localization record dated 2026-08-21 remains available through the historical reference in the release notes. The installer has not been run as part of this documentation update.

**SHA-256**

```text
c1bcc40900eb0c3f282c5657a7c3d06b69629483ec1674f4da347a295485dc3c
```

To verify a downloaded installer in PowerShell:

```powershell
Get-FileHash -LiteralPath '.\PalletPro-install-v1.4.8_260828.exe' -Algorithm SHA256
```

## Documentation

| Resource | Purpose |
| --- | --- |
| [Pallet Recognition User Guide](pallet-recognition-user-guide-eagle-m-series-camera.md) | Camera installation, application interfaces, parameter configuration, near/far teaching, calibration verification, and API/UDP/TCP/CAN communication. |
| [PalletPro Release Notes](PalletProUpdateNote.md) | English and Chinese release notes for 1.4.8_260828, including changes, terminology updates, the known limitation, and upgrade guidance. |
| [CameraSDK](https://github.com/Lanxin-MRDVS/CameraSDK) | Camera SDK and LxCameraViewer resources. The user guide explains when to use LxCameraViewer for camera configuration and when to switch to PalletPro. |

The storage-location detection and depalletizing manuals in this repository describe separate application workflows; they are not PalletPro installation or release notes.

## Maintaining PalletPro content

1. **Distribute installers through GitHub Releases.** Keep executables out of the Git file history. Preserve earlier assets and their download URLs when adding a new build.
2. **Use this page as the download index.** Update the installer filename, product version, byte size, and SHA-256 together after verifying the uploaded asset.
3. **Keep user instructions in the user guide.** Update affected procedures, screenshots, and UI labels when behavior changes, and record which application/embedded-algorithm versions were checked.
4. **Keep release history in the update note.** Add a dated section for each confirmed release or build, describing changes, compatibility, known limitations, and its installer. Preserve previous entries and do not infer changes from a filename.
5. **Keep navigation connected.** Check the PalletPro links in `README.md` and `SUMMARY.md` whenever pages are added or renamed.
6. **Use versioned tags for future releases.** A tag such as `PalletPro-v<version>-<build>` keeps each package and its notes traceable. Keep the existing `PalletPro` release available so current download links continue to work.

## Documentation items to verify

- The user guide contains earlier screenshots and UI labels. Reconcile them with the terminology recorded in the 1.4.8 update note.
- The far-end teaching distances differ between the interface explanation and the deployment procedure (sections 3.3.1 and 4.6). Confirm the intended conditions with the algorithm owner before changing either procedure.
- Confirm the supported Windows versions, matching camera firmware/embedded-algorithm versions, and upgrade/rollback steps before adding compatibility claims for build `260828`.
