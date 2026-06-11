<p align="center">
  <img src="./assets/mrdvs_logo.png" alt="MRDVS Logo" width="300">
</p>

<h1 align="center">MRDVS Application Algorithm Docs</h1>

<p align="center">
  Application algorithm documentation for MRDVS 3D vision products.<br>
  面向迈尔微视3D视觉产品的应用算法文档导航页。
</p>

<p align="center">
  <a href="https://hub.mrdvs.cn/">MRDVS Hub 2.0</a> |
  <a href="#english">English</a> |
  <a href="#中文">中文</a> |
  <a href="https://github.com/Lanxin-MRDVS/CameraSDK">CameraSDK</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/docs-application%20algorithm-2563EB" alt="Application Algorithm Docs">
  <img src="https://img.shields.io/badge/scenarios-obstacle%20avoidance%20%7C%20pallet%20recognition%20%7C%20unstacking-0F172A" alt="Application Scenarios">
  <img src="https://img.shields.io/badge/products-MRDVS%203D%20vision-0891B2" alt="MRDVS 3D Vision">
</p>

---

# English

## Contents

- [Overview](#overview)
- [Documentation](#documentation)
- [Repository Structure](#repository-structure)
- [Notes](#notes)

<a id="overview"></a>
## 🔎 Overview

This repository provides application algorithm documentation for MRDVS 3D vision products. It is intended for customers, field application engineers, technical support teams, and internal users who need to deploy, configure, and integrate MRDVS application algorithms in real scenarios.

The current documentation covers obstacle avoidance, pallet recognition, and soft bag/carton unstacking. SDK-related documents, such as CameraSDK developer guides, sample instructions, and LxCameraViewer user manuals, are maintained in the [CameraSDK repository](https://github.com/Lanxin-MRDVS/CameraSDK).

<a id="documentation"></a>
## 📚 Documentation

### Obstacle Avoidance

**Document:** [Obstacle Avoidance Algorithm Deployment Instruction](./Obstacle-Avoidance-Algorithm-Deployment-Instruction.md)

This document describes the deployment process, configuration method, and usage notes for the obstacle avoidance algorithm. It is recommended for users who need to configure obstacle detection, obstacle output, and related deployment parameters for mobile robot scenarios.

---

### Pallet Recognition

**Document:** [Pallet Recognition User Guide for Eagle M Series Camera](./pallet-recognition-user-guide-eagle-m-series-camera.md)

This document describes the pallet recognition function based on Eagle M series cameras. It covers environment configuration, operation workflow, parameter settings, and common usage notes for pallet recognition and positioning scenarios.

---

### Softbag / Carton Unstacking

**Document:** [Softbag / Carton Unstacking Algorithm Deployment Guide](./softbag-carton-unstacking-algorithm-deployment.md)

This document describes the algorithm deployment, configuration, and integration process for soft bag and carton unstacking scenarios. It is intended for users who need to integrate MRDVS vision algorithms into depalletizing or unstacking workflows.

<a id="repository-structure"></a>
## 🗂️ Repository Structure

```text
.
├── Obstacle-Avoidance-Algorithm-Deployment-Instruction.md
├── pallet-recognition-user-guide-eagle-m-series-camera.md
├── softbag-carton-unstacking-algorithm-deployment.md
└── README.md
```

<a id="notes"></a>
## 📌 Notes

- This repository is used for MRDVS application algorithm documentation.
- SDK-related documents are maintained in the CameraSDK repository.
- Select the corresponding document according to the actual application scenario.
- If a document link cannot be opened, check whether the file name in this README is consistent with the actual file name in the repository.

---

# 中文

## 目录

- [概览](#概览)
- [文档索引](#文档索引)
- [仓库结构](#仓库结构)
- [使用说明](#使用说明)

<a id="概览"></a>
## 🔎 概览

本仓库用于维护迈尔微视3D视觉产品的应用算法文档，主要面向客户开发人员、FAE、技术支持人员及内部相关人员，用于查询应用算法的部署、配置和集成说明。

当前文档覆盖避障算法、托盘识别和软包/纸箱拆垛等应用场景。CameraSDK开发指南、示例程序说明、LxCameraViewer用户手册等SDK相关文档统一维护在[CameraSDK仓库](https://github.com/Lanxin-MRDVS/CameraSDK)。

<a id="文档索引"></a>
## 📚 文档索引

### 避障算法

**文档：**[Obstacle Avoidance Algorithm Deployment Instruction](./Obstacle-Avoidance-Algorithm-Deployment-Instruction.md)

该文档用于说明避障算法的部署流程、配置方法和使用注意事项，适用于移动机器人场景下的障碍物检测、避障输出及相关部署参数配置。

---

### 托盘识别

**文档：**[Pallet Recognition User Guide for Eagle M Series Camera](./pallet-recognition-user-guide-eagle-m-series-camera.md)

该文档用于说明基于Eagle M系列相机的托盘识别功能，内容包括环境配置、使用流程、参数设置和常见使用注意事项，适用于托盘识别和托盘定位相关场景。

---

### 软包/纸箱拆垛

**文档：**[Softbag / Carton Unstacking Algorithm Deployment Guide](./softbag-carton-unstacking-algorithm-deployment.md)

该文档用于说明软包和纸箱拆垛场景下的算法部署、配置和集成流程，适用于将迈尔微视视觉算法接入拆垛、拆包或相关自动化作业流程的场景。

<a id="仓库结构"></a>
## 🗂️ 仓库结构

```text
.
├── Obstacle-Avoidance-Algorithm-Deployment-Instruction.md
├── pallet-recognition-user-guide-eagle-m-series-camera.md
├── softbag-carton-unstacking-algorithm-deployment.md
└── README.md
```

<a id="使用说明"></a>
## 📌 使用说明

- 本仓库仅维护MRDVS应用算法相关文档。
- SDK开发、示例程序、工具软件用户手册等内容请查看CameraSDK仓库。
- 请根据实际应用场景选择对应文档。
- 如果点击文档链接后出现404，请检查README中的文件名是否与仓库内实际文件名完全一致。

---

<p align="center">
  <sub><em>Last updated: June 2026</em></sub><br>
  <sub><em>Hangzhou Lanxin Technology Co., Ltd. & MRDVS Co., Ltd.</em></sub><br>
  <sub><em>All Rights Reserved.</em></sub>
</p>
