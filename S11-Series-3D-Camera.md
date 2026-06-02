## 1. Product Overview

### 1.1 Introduction

The MRDVS S11 is a solid-state RGB-D camera based on dToF (direct Time-of-Flight) technology, designed specifically for mobile robots. Available with Ethernet and USB interfaces, the S11 provides real-time depth perception with up to 1cm accuracy within 0.1–5m range (max), simultaneously outputting depth data, RGB images, and IR amplitude data. It delivers a cost-effective, high-stability vision solution for obstacle avoidance, spatial awareness, and environmental modeling in mobile robotics.

A MIPI interface custom module is also available, offering identical core performance with variations in communication interface, dimensions, and power supply to meet diverse integration requirements.

![S11 Camera](https://i.ibb.co/0Rj9Pnyg/cfa8d3dc-62ff-4008-ae47-9661f344d9c7.png)

### 1.2 Key Features

- **dToF Depth Sensing**: Measures laser signal round-trip time directly to calculate distance. Compared to iToF, dToF offers higher accuracy (≤1cm), longer effective range (0.1–5m), and stronger resistance to ambient light interference outdoors.
- **Multi-stream Synchronous Output**: Simultaneously outputs depth maps, RGB images, and IR amplitude data without acquisition latency.
- **Solid-state Design**: No moving mechanical parts. Compact form factor (90×25×25 mm), lightweight (approx. 130g Ethernet, 90g USB), with superior shock resistance and stability. Custom MIPI modules available (120°: 33×18×12mm; 140°: 33×18×13mm).

### 1.3 Applications

1. Cleaning robots (ground obstacle detection)
2. Industrial mobile robots (AGV/AMR)
3. Service robots (guidance, delivery)
4. Home companion robots (environmental perception)
5. Special-purpose robots (low-temperature, humid environments)

---

## 2. Specifications

| Parameter | S11 Ethernet | S11 USB | S11 MIPI |
|------------|-------------|---------|----------|
| **Environment** | Indoor/Outdoor | Indoor/Outdoor | Indoor/Outdoor |
| **Depth Technology** | dToF | dToF | dToF |
| **Laser Wavelength** | 940nm | 940nm | 940nm |
| **Depth Range** | 0.1–5m (118°), 0.1–3m (140°), 10%–90% reflectivity | 0.1–3m (140°), 10%–90% reflectivity | 0.1–5m (118°), 0.1–3m (140°), 10%–90% reflectivity |
| **Depth Accuracy** | 1cm | 1cm | 1cm |
| **Output Data** | Depth (point cloud), RGB, IR (amplitude) | Depth (point cloud), RGB, IR (amplitude) | Depth (point cloud), RGB, IR (amplitude) |
| **Depth Resolution/Frame Rate** | 240×96@max. 20fps/10fps (typical) | 240×96@max. 20fps/10fps (typical) | 240×96@max. 20fps/10fps (typical) |
| **Depth FOV** | 118°×44°±3° / 140°×56°±3° | 140°×56°±3° | 118°×44°±3° / 140°×56°±3° |
| **RGB Resolution/Frame Rate** | 1280×1080@max. 20fps/10fps (typical) | 1280×1080@max. 20fps/10fps (typical) | N/A |
| **RGB FOV** | 120°×110°±3° | 120°×110°±3° | N/A |
| **RGB-D Alignment** | Supported | Supported | N/A |
| **Data Interface** | Ethernet | USB | MIPI |
| **Operating Temperature** | -20°C ~ 60°C | -20°C ~ 60°C | N/A |
| **Storage Temperature** | -40°C ~ 70°C | -40°C ~ 70°C | N/A |
| **Time Synchronization** | PTP | PTP | N/A |
| **Protection Rating** | IP54 (Ethernet) | N/A | N/A |
| **Eye Safety** | Class I | Class I | Class I |
| **Dimensions** | 90×25×25mm | 90×25×25mm | 33×18×12mm (120°), 33×18×13mm (140°) |
| **Weight** | ~130g (Ethernet), ~90g (USB) | ~90g | <10g |
| **Power Consumption** | <4W (avg), 13W (peak) | <4W (avg), 30W (peak) | ≤2W (avg), 8W (peak) |
| **Power Supply** | 12V–28V DC | 5V USB 3.0 | 3.3V/5V DC |
| **Software Environment** | C/C++/ROS SDK | C/C++/ROS SDK | C/C++/ROS SDK |
| **System Support** | Windows 7/8/10/11, Linux, Arm Linux/ROS | Windows 7/8/10/11, Linux, Arm Linux/ROS | Windows 7/8/10/11, Linux, Arm Linux/ROS |
| **Ambient Light Immunity** | 100 kLux | 100 kLux | 100 kLux |

---

## 3. Product Structure

![S11 Ethernet Dimensions](https://i.ibb.co/3YF0R0FS/a7e9439d-0b98-4283-a3b8-b3ec843cadbc.png)

**S11 Ethernet Dimensions**

![S11 USB Dimensions](https://i.ibb.co/LdhjrLdC/c793856e-0c27-4797-a05b-b410a1673bc5.png)

**S11 USB Dimensions**

![S11 MIPI 120°](https://i.ibb.co/x8Sw6WKz/4aec9582-db51-478b-9fb8-9acd053c03d7.png)

**S11 MIPI 120°**

![S11 MIPI 140°](https://i.ibb.co/wNhSvKr8/a6a5216a-3534-4c63-bde1-8726bc1f742f.png)

**S11 MIPI 140°**

---

## 4. Integration Guide

### 4.1 Detection Range

**1. S11 140°×56°±3° Field of View (2D Diagram)**

![140° FOV](https://i.ibb.co/mKxrMW6/32c5e22d-646a-4942-be2e-fea2917c797b.png)

**2. S11 118°×44°±3° Field of View (2D Diagram)**

![118° FOV](https://i.ibb.co/9SVGnMr/07baae09-6c2a-4136-8367-99f7b8b07bb0.png)

### 4.2 Critical Installation Requirements

#### 4.2.1 Recommended Mounting

When installing the 3D vision camera, ensure the clearance zone shown in the diagram remains completely unobstructed. Any object intrusion within this zone will directly interfere with point cloud data, causing image noise, false obstacle detection, or data anomalies.

![Clearance Zone](https://i.ibb.co/SXpr4HpY/0449536b-6ccf-4cc7-9ba9-f3c0d66dee1e.png)

#### 4.2.2 Common Installation Errors

Improper installation environments can interfere with ToF measurement principles, causing operational failures:

**1. Physical Obstruction and FOV Truncation**

Structural frames, ribs, or other components intruding into the sensor's nominal FOV, or eccentric mounting with undersized openings, cause FOV cropping. The sensor may misidentify structural elements as targets. Symptoms include fixed blind zones, false short-range measurements, and compressed FOV, leading to missed obstacle detection and path planning errors.

**2. Near-field IR Interference and Reflection**

The most common failure cause in confined installations involves abnormal IR reflection:

- **Multi-path interference**: IR light reflecting multiple times from structural walls alters detection timing, causing distance calculation errors.
- **Specular reflection**: Highly reflective smooth surfaces (polished metal, mirrors) cause mirror-like reflections, resulting in localized signal loss or saturation.
- **Highlight contamination**: When the sensor is <10cm from bright, smooth structural elements, strong reflections cause receiver saturation. For iToF cameras, this phase disturbance prevents ToF calculation. This interference causes data distortion, accelerates receiver aging, and impairs core functionality.

**3. Optical Window Interference**

Protective glass or optical windows in front of the sensor can cause interference:

- **Multi-reflection artifacts**: Reflections from window surfaces create ghost images mixed with valid signals, causing depth map doubling and point cloud duplication.
- **Contamination and fogging**: Enclosed spaces promote fogging and dust accumulation on windows, reducing signal-to-noise ratio.
- **Material mismatch**: Standard glass or acrylic may block signals entirely, causing complete data loss. Use high-transmission optical glass instead.

**4. Other Hidden Factors**

- **Mounting stress**: Excessive clamping force causes lens deformation and optical axis offset. For ToF cameras, optical axis offset creates distance measurement errors.
- **Thermal interference**: Poor heat dissipation in enclosed spaces causes sensor temperature rise and window thermal deformation, leading to ranging drift and long-term failure.

### 4.3 SDK

Refer to the MRDVS Host Computer Software Manual and SDK Development Guide.

### 4.4 Environmental and Reliability Specifications

| Item | Specification |
|------|---------------|
| **Operating Environment** | Temperature: -20°C ~ 60°C |
| | Illumination: 0–100 kLux |
| **Storage Environment** | Temperature: -40°C ~ 70°C |
| | Humidity: Max 90% RH |
| **Normal Operating Temperature Rise** | Housing temperature rise <25°C |
| **ESD Rating** | Contact discharge ±4KV, air discharge ±8KV |
| **RE Rating** | Compliant with GB 9254 Class A |
| **Operating Life** | 3 years |
| **Environmental Compliance** | RoHS |

---

## 5. Quick Start Guide

### 5.1 Connection and Testing

![Connection Diagram](https://i.ibb.co/HD450P6n/b2df4d53-b802-4387-b1ca-b8e45f0a5ac5.png)

#### 5.1.1 Power Supply

1. Connect the DC power cable to the camera's DC power port and to a 24V/2A DC power adapter.
2. Check the power indicator. Slow blue flashing indicates normal power-on status.
3. If the indicator remains off or shows abnormal status (e.g., solid red), verify the power connection and adapter functionality.

#### 5.1.2 Network Configuration

1. Connect the camera's communication port directly to the computer using a Cat6 Ethernet cable.
2. Default IP address: 192.168.100.82.
3. Configure the computer IP to the same subnet and disable the firewall.

#### 5.1.3 Software Operation

1. Launch the host computer software to acquire camera images. Verify image clarity and absence of artifacts or lag to confirm proper connection.
2. Refer to section 5.2 or the LxCameraViewer Host Computer Software Manual for detailed operation instructions.
3. Contact MRDVS sales or technical support for additional assistance.

### 5.2 Interface Overview

LxCameraViewer host computer software supports multiple device connections and viewing. It displays depth maps, amplitude maps, point clouds, and RGB output. The software enables reading and setting camera parameters and algorithm configurations. Users can view and save image data, camera configurations, and algorithm details.

The interface consists of three main areas: the device list (blue zone 1), menu bar (green zone 2), and image display (red zone 4). Double-click the menu bar to maximize/minimize; drag by holding the left mouse button.

![Interface Overview (Camera Closed)](https://i.ibb.co/h1rhy1vn/a70d39dd-1006-4527-9dc8-c75198c2a986.png)

After opening a camera, the right-side function panel (zone 3) appears. Click "Basic Tools," "Applied Algorithms," or "Others" menus to access features. Basic tools include image display, 2D/3D settings, and filtering.

![Interface Overview (Camera Open)](https://i.ibb.co/QFTdXVhX/2667b6e5-8fbf-4e8e-943c-55019cd885f1.png)

The device list is located at the upper left. Click **[Open]** or **[Close]** to control the camera. The middle-left panel displays camera info, software operations, operation results, and streaming status. Device information appears at the lower left, showing details for the selected device.

Click **[Stream]** to start/stop image acquisition. The button disables during operation until completion. Click **[Single Capture]** to save images from active streams. Check **[Depth]**, **[Amplitude]**, **[RGB]**, or **[Point Cloud]** boxes to enable corresponding image formats.

For detailed information, refer to the LxCameraViewer Host Computer Software Manual.

---

## 6. Troubleshooting

| Issue | Solution |
|-------|----------|
| Camera does not respond when clicked | Check and disable firewall settings to ensure communication is not blocked |
| Host computer software detects multiple IP addresses | IP conflict detected on network. Manually select the correct IP address to open the camera |
| Unstable data stream after opening camera | Use Gigabit Ethernet cable. Fast Ethernet cables may cause initial data transmission instability |
| Software installation location issues | Default installation to C: drive may cause permission issues. Select a directory with appropriate read/write permissions |

---

## 7. Safety Information

![Safety Warning](https://i.ibb.co/201QKvZh/8e6fe3fb-d466-4347-be43-b9139e15f0b3.png)
