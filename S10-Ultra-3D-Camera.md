## Product Overview

The MRDVS S10Ultra is a compact, wide-field-of-view, high-performance industrial-grade RGB-D camera. Based on dToF technology, it provides high-precision depth data from 0.2 m to 42 m for both indoor and outdoor environments. The camera delivers spatially and temporally aligned RGB and depth data, and features a built-in IMU (output frequency up to 200 Hz) to effectively support mainstream SLAM algorithms such as FastLIO and [FastLIO2](https://github.com/Lanxin-MRDVS/MRDVS-S10Ultra_Mapping). With an integrated SoC and software trigger support, the S10Ultra is also available as an MIPI module.

![](https://hub.mrdvs.cn/static-file/a2ec1932-73d9-4c34-b1f4-045ea8ceb946/b57c7d10-1a66-4d79-aefc-e3706f78f6f8.png)

## Key Technology and Applications

- **dToF Depth Sensing**: Directly measures the round-trip time of laser signals to calculate distance, enabling an extended detection range (0.2–42 m) and strong ambient light immunity (100 kLux).
- **Multi-Data Synchronous Output**: Simultaneously outputs depth maps, high-quality RGB images, and IR amplitude maps with spatial and temporal synchronization.
- **All-Solid-State Design**: No moving parts; compact form factor (106 × 69 × 43 mm) with superior shock resistance and stability. Provides RGB-D aligned data.

**Primary Applications**

- **Robotic Lawn Mowers**: Enables precise localization and navigation for autonomous operation in gardens and lawns.
- **Industrial Quadruped Robots**: Enhances localization, navigation, and environmental perception for robot dogs in inspection and exploration scenarios.
- **Multi-Rotor Drones**: Improves localization, navigation, obstacle avoidance, and environmental perception for drones in inspection and surveying missions.

![](https://hub.mrdvs.cn/static-file/74e53d10-47b1-47c1-8495-da341b854496/6fa61ae1-77db-4510-8ad0-982542a2afa3.png "Figure 1. S10 Ultra Equipped Quadruped Robot")

![](https://hub.mrdvs.cn/static-file/9f317e34-29b9-4e0d-a405-89afd7f6c34f/2d4a23b0-1117-475a-a700-93ed73a86400.png "Figure 2. Robotic Lawn Mower with S10Ultra")

![](https://hub.mrdvs.cn/static-file/0378bc88-1491-4152-8f03-8e0eb6964b5c/183ae5da-42dd-4200-bb67-3299d2a212f0.png "Figure 3. Multi-Rotor Drone Application")

## Specifications

| Parameter | S10Ultra |
|-----------|----------|
| Operating Environment | Indoor / Outdoor |
| Depth Technology | dToF |
| Laser Wavelength | 940 nm |
| Depth Range | 0.2–42 m (@ 90% reflectivity) / 0.2–30 m (@ 10% reflectivity) |
| Range Accuracy | ≤ 4 cm |
| Output Data | Depth (point cloud) / RGB / IR (amplitude) |
| Depth Resolution / Frame Rate | 240 × 160 @ Max 10 fps / 10 fps (typical) |
| Depth FOV | 120° × 80° ± 3° |
| RGB Resolution / Frame Rate | 1280 × 1080 @ Max 20 fps / 10 fps (typical) |
| RGB FOV | 120° × 110° ± 3° |
| RGB-D Alignment | Supported |
| Data Interface | Ethernet |
| Operating Temperature | -20°C ~ 75°C |
| Storage Temperature | -40°C ~ 85°C |
| Time Synchronization | PTP |
| Protection Rating | IP67 |
| Eye Safety | Class I |
| Dimensions | 106 × 69 × 43 mm |
| Weight | ~440 g |
| Power Consumption | < 9 W |
| Power Supply | 12–27 V DC |
| Software Environment | C/C++/ROS SDK |
| OS Support | Windows 7/8/10/11, Linux, Arm Linux / ROS |
| Ambient Light Immunity | 100 kLux |
| IMU Output Frequency | 200 Hz |

## Mechanical Design and Software

### Mechanical Dimensions

![](https://hub.mrdvs.cn/static-file/2aa056c7-b51d-4adf-962b-ee8bd931f064/9dae8fb1-222d-495e-bc60-8f403e451934.jpg)

### Software SDK

Refer to the MRDVS Host Software User Manual and the SDK Development Guide.

## Integration Guide

| Item | | Specification |
|------|-|---------------|
| Operating Environment | Temperature | -20°C ~ 75°C |
| | Illumination | 0 kLux ~ 100 kLux |
| Storage Environment | Temperature | -40°C ~ 85°C |
| | Humidity | Relative humidity: Max 90% RH |

## Detection Range

![](https://hub.mrdvs.cn/static-file/d2c3be3a-bf40-44fe-9fa7-e9a06fbab482/d7b9eb6a-d928-4bca-8cfe-883234e52c63.png)

## Critical Installation Requirements

### Recommended Installation

When installing the 3D vision camera, ensure the clearance zone shown in the diagram remains completely unobstructed. Any object intrusion within this zone will directly interfere with point cloud data, causing image noise, false obstacle detection, or data anomalies.

![](https://hub.mrdvs.cn/static-file/6adbdf3c-c914-456a-9777-5a4721879f16/d195c008-fd7a-4674-953f-f37919a40b89.png)

### Installation Failure Causes

Improper installation environments can interfere with Time-of-Flight measurement and triangulation principles, causing operational failures. Specific causes include:

**1. Physical Obstruction and FOV Truncation**

Structural frames, ribs, or other components intruding into the sensor's nominal field of view, or eccentric mounting with undersized openings, cause FOV cropping. The sensor may misidentify structural elements as targets. Typical symptoms include fixed blind zones, false short-range measurements, and compressed FOV, leading to missed obstacle detection and path planning errors.

**2. Near-Field IR Interference and Reflection**

The most common failure cause in confined installations is abnormal IR reflection. This falls into three categories:

- **Multi-path interference**: IR light reflecting multiple times from structural walls alters detection timing, causing distance calculation errors.
- **Specular reflection**: Highly reflective smooth surfaces (polished metal, mirrors) cause mirror-like reflections, resulting in localized signal loss or saturation.
- **Highlight contamination**: When the sensor is less than 10 cm from bright, smooth structural elements, strong reflections cause receiver saturation. Phase disturbance prevents ToF calculation, causing data distortion, accelerated receiver aging, and impaired core functionality.

**3. Optical Window Interference**

Protective glass or optical windows in front of the sensor can cause interference due to material or cleanliness issues. This falls into three categories:

- **Multi-reflection artifacts**: Reflections from window surfaces create ghost images mixed with valid signals, causing depth map doubling and flying pixels.
- **Contamination and fogging**: Enclosed spaces promote fogging and dust accumulation on windows, reducing signal-to-noise ratio.
- **Material mismatch**: Standard glass or acrylic may block signals entirely, causing complete data loss. Replace with high-transmission optical glass to improve performance.

Window interference increases measurement error, may damage the lens, and raises maintenance costs.

**4. Other Hidden Factors**

- **Mounting stress**: Excessive clamping force causes lens deformation and optical axis offset, creating distance measurement errors in ToF cameras.
- **Thermal interference**: Poor heat dissipation in enclosed spaces causes sensor temperature rise and window thermal deformation, leading to ranging drift and potential long-term failure.

## Quick Start Guide

### Connection and Testing

![](https://hub.mrdvs.cn/static-file/3b17fd5d-5aee-40d8-90bd-be711fd0ea96/84ce70a3-9bfd-46d9-961d-a4d57091a8cb.png)

*Connection diagram*

### Power Supply

- Connect the DC power cable to the camera's DC power port and to a 12–27 V / 3 A DC power adapter.
- Check the power indicator. Slow blue flashing indicates normal power-on status.
- If the indicator remains off or shows abnormal status (e.g., solid red), verify the power connection and adapter functionality.

### Network Configuration

- Connect the camera's communication port directly to the computer using a Cat6 Ethernet cable.
- Default IP address: 192.168.100.82.
- Configure the computer IP to the same subnet and disable the firewall.

### Software Operation

- Launch the host software to acquire camera images. Verify image clarity and absence of artifacts or lag to confirm proper connection.
- Refer to the Interface Overview section below or the LxCameraViewer Host Software User Manual for detailed instructions.
- Contact MRDVS sales or technical support for additional assistance.

## Interface Overview

The LxCameraViewer host software supports multiple device connections and viewing. It displays depth maps, amplitude maps, point clouds, and RGB output. The software enables reading and setting camera parameters and algorithm configurations. Users can view and save image data, camera configurations, and algorithm details.

The interface consists of three main areas: the device list (blue zone 1), menu bar (green zone 2), and image display (red zone 4). Double-click the menu bar to maximize/minimize; drag by holding the left mouse button.

![](https://hub.mrdvs.cn/static-file/039de4f0-71e7-4a2e-a01c-a7f17bd8f4e8/e6945a49-8ace-487b-a38c-793ff8bfbf99.png)

*Interface overview (camera closed)*

After opening a camera, the right-side function panel (zone 3) appears. Click **Basic Tools**, **Applied Algorithms**, or **Others** to access features. Basic tools include image display, 2D/3D settings, and filtering.

![](https://hub.mrdvs.cn/static-file/3d8475ee-e7db-4454-a232-72d54359f815/21260dfa-61bc-493e-843c-f5d8cd8c2fdc.png)

*Interface overview (camera open)*

The device list is located at the upper left. Click **[Open]** or **[Close]** to control the camera. The middle-left panel displays camera info, software operations, operation results, and streaming status. Device information appears at the lower left, showing details for the selected device.

Click **[Stream]** to start/stop image acquisition. The button disables during operation until completion. Click **[Single Capture]** to save images from active streams. Check **[Depth]**, **[Amplitude]**, **[RGB]**, or **[Point Cloud]** to enable the corresponding image formats.

For detailed information, refer to the LxCameraViewer Host Software User Manual.

## Laser Safety Classification

![](https://hub.mrdvs.cn/static-file/3e69ba1d-2ef0-43c0-a1f1-e0d6678e1f89/3fadcf0c-5f15-49e3-9c07-631fef6c3faa.png)

## Troubleshooting

| No. | Issue | Solution |
|-----|-------|----------|
| 1 | No response when opening the camera | Check whether the firewall is disabled; disable it if necessary. |
| 2 | Host software detects multiple IPs | Duplicate IP addresses detected on the LAN. Select the required IP to open the camera. |
| 3 | Unstable data after opening the camera | Use a Gigabit Ethernet cable; data may be unstable initially with a Fast Ethernet cable. |
| 4 | Software installation location | Default installation to C: drive may cause permission issues. |

### S10Ultra Featured at IROS 2025

![](https://hub.mrdvs.cn/static-file/4039bcf6-5835-435c-9acc-a3772876c353/c9b68b10-48f7-4f85-ad89-64e51a072bb0.png)
