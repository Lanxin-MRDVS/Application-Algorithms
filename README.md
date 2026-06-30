<div align="center"><img src=".gitbook/assets/mrdvs_logo.png" alt="MRDVS Logo" width="300"></div>

<h2 align="center">MRDVS Algorithm Deployment Guide</h2>

<p align="center"><a href="https://github.com/Lanxin-MRDVS/CameraSDK">CameraSDK</a></p>

<div align="center"><img src="https://img.shields.io/badge/docs-application%20algorithm-2563EB" alt="Application Algorithm Docs"> <img src="https://img.shields.io/badge/scenarios-obstacle%20avoidance%20|%20pallet%20recognition%20|%20unstacking-0F172A" alt="Application Scenarios"> <img src="https://img.shields.io/badge/products-MRDVS%203D%20vision-0891B2" alt="MRDVS 3D Vision"></div>

***

### Contents

* [Overview](./#overview)
* [Documentation](./#documentation)
* [Repository Structure](./#repository-structure)
* [Notes](./#notes)

### 🔎 Overview

This repository provides application algorithm documentation for MRDVS 3D vision products. It is intended for customers, field application engineers, technical support teams, and internal users who need to deploy, configure, and integrate MRDVS application algorithms in real scenarios.

The current documentation covers obstacle avoidance, pallet recognition, and soft bag/carton unstacking. SDK-related documents, such as CameraSDK developer guides, sample instructions, and LxCameraViewer user manuals, are maintained in the [CameraSDK repository](https://github.com/Lanxin-MRDVS/CameraSDK).

### 📚 Documentation

#### Obstacle Avoidance

**Document:** [Obstacle Avoidance Algorithm Deployment Instruction](Obstacle-Avoidance-Algorithm-Deployment-Instruction.md)

This document describes the deployment process, configuration method, and usage notes for the obstacle avoidance algorithm. It is recommended for users who need to configure obstacle detection, obstacle output, and related deployment parameters for mobile robot scenarios.

***

#### Pallet Recognition

**Document:** [Pallet Recognition User Guide for Eagle M Series Camera](pallet-recognition-user-guide-eagle-m-series-camera.md)

This document describes the pallet recognition function based on Eagle M series cameras. It covers environment configuration, operation workflow, parameter settings, and common usage notes for pallet recognition and positioning scenarios.

***

#### Softbag / Carton Unstacking

**Document:** [Softbag / Carton Unstacking Algorithm Deployment Guide](softbag-carton-unstacking-algorithm-deployment.md)

This document describes the algorithm deployment, configuration, and integration process for soft bag and carton unstacking scenarios. It is intended for users who need to integrate MRDVS vision algorithms into depalletizing or unstacking workflows.

### 🗂️ Repository Structure

```
.
├── Obstacle-Avoidance-Algorithm-Deployment-Instruction.md
├── pallet-recognition-user-guide-eagle-m-series-camera.md
├── softbag-carton-unstacking-algorithm-deployment.md
└── README.md
```

### 📌 Notes

* This repository is used for MRDVS application algorithm documentation.
* SDK-related documents are maintained in the CameraSDK repository.
* Select the corresponding document according to the actual application scenario.
* If a document link cannot be opened, check whether the file name in this README is consistent with the actual file name in the repository.

***

<p align="center"><sub><em>Last updated: June 2026</em></sub><br><sub><em>Hangzhou Lanxin Technology Co., Ltd. & MRDVS Co., Ltd.</em></sub><br><sub><em>All Rights Reserved.</em></sub></p>
