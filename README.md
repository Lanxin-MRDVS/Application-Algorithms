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

- [Contents](#contents)
- [Overview](#-overview)
- [Documentation](#-documentation)
- [Scenario Guide](#-scenario-guide)
- [Repository Structure](#️-repository-structure)
- [Related Repository](#-related-repository)
- [Notes](#-notes)

## 🔎 Overview

This repository provides application algorithm documentation for MRDVS 3D vision products. It is intended for customers, field application engineers, technical support teams, and internal users who need to deploy, configure, and integrate MRDVS application algorithms in real scenarios.

The current documentation covers obstacle avoidance, pallet recognition, and soft bag/carton unstacking. SDK-related documents, such as CameraSDK developer guides, sample instructions, and LxCameraViewer user manuals, are maintained in the [CameraSDK repository](https://github.com/Lanxin-MRDVS/CameraSDK).

## 📚 Documentation

| Category | Document | Description |
| --- | --- | --- |
| Obstacle Avoidance | [Deployment Guide](./Obstacle-Avoidance-Algorithm-Deployment-Instruction.md) | Deployment and configuration guide for the obstacle avoidance algorithm. |
| Pallet Recognition | [User Guide](./pallet-recognition-user-guide-eagle-m-series-camera.md) | User guide for pallet recognition based on Eagle M series cameras, including setup, usage, and parameter configuration. |
| Softbag / Carton Unstacking | [Deployment Guide](./softbag-carton-unstacking-algorithm-deployment-guide.md) | Deployment guide for soft bag and carton unstacking scenarios, including algorithm setup and integration instructions. |

## 🧩 Scenario Guide

| Scenario | Typical Use | Recommended Document |
| --- | --- | --- |
| Mobile robot obstacle avoidance | Configure obstacle detection, avoidance output, and related deployment parameters. | [Obstacle Avoidance Deployment Guide](./Obstacle-Avoidance-Algorithm-Deployment-Instruction.md) |
| Forklift pallet recognition | Configure Eagle M series cameras for pallet recognition and positioning. | [Pallet Recognition User Guide](./pallet-recognition-user-guide-eagle-m-series-camera.md) |
| Robotic depalletizing / unstacking | Deploy algorithms for soft bag and carton unstacking applications. | [Softbag / Carton Unstacking Deployment Guide](./softbag-carton-unstacking-algorithm-deployment-guide.md) |

## 🗂️ Repository Structure

```text
.
|-- Obstacle-Avoidance-Algorithm-Deployment-Instruction.md
|-- pallet-recognition-user-guide-eagle-m-series-camera.md
|-- softbag-carton-unstacking-algorithm-deployment-guide.md
|-- assets
`-- README.md
```

## 🔗 Related Repository

| Repository | Description |
| --- | --- |
| [Lanxin-MRDVS/CameraSDK](https://github.com/Lanxin-MRDVS/CameraSDK) | SDK package, developer guides, sample programs, CameraSDK documents, and LxCameraViewer user manuals. |

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
- [场景导航](#场景导航)
- [仓库结构](#仓库结构)
- [相关仓库](#相关仓库)
- [使用说明](#使用说明)

## 🔎 概览

本仓库用于维护迈尔微视3D视觉产品的应用算法文档，主要面向客户开发人员、FAE、技术支持人员及内部相关人员，用于查询应用算法的部署、配置和集成说明。

当前文档覆盖避障算法、托盘识别和软包/纸箱拆垛等应用场景。CameraSDK开发指南、示例程序说明、LxCameraViewer用户手册等SDK相关文档统一维护在[CameraSDK仓库](https://github.com/Lanxin-MRDVS/CameraSDK)。

## 📚 文档索引

| 类别 | 文档 | 说明 |
| --- | --- | --- |
| 避障算法 | [部署指南](./Obstacle-Avoidance-Algorithm-Deployment-Instruction.md) | 用于说明避障算法的部署流程、配置方法和使用注意事项。 |
| 托盘识别 | [用户指南](./pallet-recognition-user-guide-eagle-m-series-camera.md) | 用于说明基于Eagle M系列相机的托盘识别功能，包括环境配置、使用流程和参数设置。 |
| 软包/纸箱拆垛 | [部署指南](./softbag-carton-unstacking-algorithm-deployment-guide.md) | 用于说明软包和纸箱拆垛场景下的算法部署、配置和集成流程。 |

## 🧩 场景导航

| 应用场景 | 典型用途 | 推荐文档 |
| --- | --- | --- |
| 移动机器人避障 | 配置障碍物检测、避障输出及相关部署参数。 | [避障算法部署指南](./Obstacle-Avoidance-Algorithm-Deployment-Instruction.md) |
| 叉车托盘识别 | 配置Eagle M系列相机，用于托盘识别和定位。 | [托盘识别用户指南](./pallet-recognition-user-guide-eagle-m-series-camera.md) |
| 机器人拆垛/拆包 | 部署软包、纸箱等场景下的拆垛应用算法。 | [软包/纸箱拆垛算法部署指南](./softbag-carton-unstacking-algorithm-deployment-guide.md) |

## 🗂️ 仓库结构

```text
.
|-- Obstacle-Avoidance-Algorithm-Deployment-Instruction.md
|-- pallet-recognition-user-guide-eagle-m-series-camera.md
|-- softbag-carton-unstacking-algorithm-deployment-guide.md
|-- assets
`-- README.md
```

## 🔗 相关仓库

| 仓库 | 说明 |
| --- | --- |
| [Lanxin-MRDVS/CameraSDK](https://github.com/Lanxin-MRDVS/CameraSDK) | 用于维护SDK包、开发指南、示例程序、CameraSDK相关文档和LxCameraViewer用户手册。 |

## 📌 使用说明

- 本仓库仅维护MRDVS应用算法相关文档。
- SDK开发、示例程序、工具软件用户手册等内容请查看CameraSDK仓库。
- 请根据实际应用场景选择对应文档。
- 如果点击文档链接后出现404，请检查README中的文件名是否与仓库内实际文件名完全一致。

---

<p align="center">
  <sub><em>Last updated: April 2026</em></sub><br>
  <sub><em>Hangzhou Lanxin Technology Co., Ltd. & MRDVS Co., Ltd.</em></sub><br>
  <sub><em>All Rights Reserved.</em></sub>
</p>
