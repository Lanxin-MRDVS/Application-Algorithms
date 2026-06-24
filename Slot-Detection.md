# Slot Detection system deployment

## 1. Introduction

In modern smart warehousing and logistics automation, slot detection serves as the critical bridge connecting the physical space with digital information flows. Accurate and real-time identification of slot status not only determines the safety and continuity of automated handling equipment (such as AGVs and stacker cranes) but also acts as the fundamental cornerstone for ensuring high consistency between the digital records in the Warehouse Management System and the actual physical inventory.

This manual is specifically designed for the deployment of the StockSync algorithm, powered by the MRDVS S10 Ultra camera system. Integrating the S10 Ultra's advanced 3D visual perception capabilities with the intelligent StockSync algorithm, this solution is engineered to achieve high-precision, low-latency recognition of slot states, including "occupied," "empty," and "item posture"—even in complex and dynamic warehousing environments. By deploying this integrated hardware and software system, enterprises can effectively eliminate manual inventory discrepancies, optimize storage space utilization, and provide reliable data support for upstream and downstream automated operations.


## 2. Camera Hardware Installation Guide

**Camera Hardware**
| Device | LiDAR | Algorithm |
| :--- | :--- | :--- |
| S10 Ultra | mid360 | StockSync |

### 2.1 Camera Installation

The camera must be secured using a bracket. You can use the mounting method and bracket illustrated in the diagram below.

### 2.2 Camera connections

The camera is powered by a 24V DC supply and connected via a Cat6a or Cat7 Ethernet cable. After the camera is installed and deployed, connect a laptop and open the control platform LxCameraViewer to perform extrinsic parameter calibration and configure the detection range. The algorithm runs in real-time directly on the camera.

When deploying multiple cameras, connect them through a Gigabit Ethernet switch. Based on the installation heights planned in the CAD layout, securely mount the 3D vision cameras to their designated positions using the appropriate brackets. Once the cameras are installed, connect them to a regulated 24V DC power supply and link them to the switch or main controller using the corresponding Ethernet cables.

After the preparation is complete, place test items in the slots within the cameras' field of view, and then proceed with the software deployment.

### 2.3 Camera network configuration

Before connecting the camera, please complete the following setup: The factory default IP address of the camera is 192.168.100.82. Ensure that your local network port (or Ethernet adapter) is configured to be in the same subnet before establishing a connection.

Disable the firewall.

For more details about IP and Firewall configuration, please see the LxCameraViewer use manual at https://github.com/Lanxin-MRDVS/CameraSDK/wiki/LxCameraViewer-User-Manual

### 2.4 


