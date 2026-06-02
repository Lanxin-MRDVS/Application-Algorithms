## Product Overview

The MRDVS S10 series comprises compact, high-performance, industrial-grade RGB-D cameras offering exceptional value. With extended ranging capabilities, the standard version covers 0.3–8m, while the Pro version extends to 17m. The camera provides spatially and temporally aligned RGB and depth data. Featuring integrated SoC processing, it outputs depth maps, amplitude maps, RGB images, point clouds, and obstacle detection results. The Ethernet interface supports data transmission, while 2-channel IO input and 2-channel IO output enable switching between 4 obstacle avoidance zones and direct signaling for emergency stop, slow-down, and safety states.

![S10 Camera](https://i.ibb.co/Vc6xXHth/2c607248-0be3-4a00-a1b1-8c5416ce1b5e.png)

## Key Features

**Precision Long-Range Perception with Motion Blur Resistance**

Using dToF technology, the camera delivers accurate distance measurements in complex indoor and outdoor dynamic environments, providing stable, clear depth data for fast-moving autonomous vehicles, forklifts, and drones.

![Dynamic Range](https://i.ibb.co/7tC3sM0B/01a91065-1cc5-46e4-8c62-85a43fd30c2c.png)

![Indoor/Outdoor Performance](https://i.ibb.co/60wGcjCt/06972c91-49bd-4410-a9de-5bf4d80c81c4.png)

**Strong Multi-Path Interference Resistance**

Compared to iToF, the S10 better handles reflected signal overlap and interference in confined environments, providing more reliable distance measurement data.

**High-Reflectivity Object and Dynamic Range Adaptability**

When facing high-reflectivity objects in the scene, the S10 extracts depth information more accurately, ensuring stability and high performance in high-dynamic-range environments.

**Low Power Consumption with High Response Speed**

The S10 maintains low power consumption while achieving fast response rates (up to 20fps for S10, 10fps for S10 Pro), ensuring timely response to sudden obstacles in real-time applications.

**Multi-Device Concurrent Operation**

Optimized dToF chipset prevents inter-device interference, supporting multiple cameras operating simultaneously in collaborative robotics environments.

**Direct Sunlight Operation**

With strong sunlight immunity up to 100 kLux, the S10 achieves 8m ranging at 90% reflectivity (S10) and 17m (S10 Pro).

![Sunlight Performance](https://i.ibb.co/CpwS66yY/2c6c67e9-4cca-42e2-9dd5-13242a7a4862.png)

**Integrated Obstacle Avoidance with IO Output**

Two operation modes available: transmit point cloud data via Ethernet for integration with existing systems, or use the built-in obstacle avoidance algorithm to send slow-down or stop commands directly through IO ports to the controller.

## Functional Capabilities

- Low-power dToF technology in compact form factor
- Onboard computing with obstacle detection output for plug-and-play deployment
- Environmental adaptability: operates from darkness to 100 kLux sunlight, indoor to outdoor
- Extended measurement range: 0.3–8m (standard), 0.3–17m (Pro version)

## Specifications

| Parameter | S10 (Lite version available) | S10Pro |
|-----------|------------------------------|--------|
| Laser wavelength | 940 nm | 940 nm |
| Output format | Depth (point cloud), RGB, IR (amplitude) | Depth (point cloud), RGB, IR (amplitude) |
| ToF resolution/frame rate | 240×160 @Max. 20fps, typical 15fps | 240×160 @Max. 10fps, typical 10fps |
| ToF FOV | 90°×60°±3° / 120°×80°±3° | 61°×90°±3° |
| RGB resolution/frame rate | 1920×1080 @Max. 20fps, typical 15fps / 1632×1224 @Max. 20fps, typical 15fps | 1920×1080 @Max. 10fps, typical 10fps |
| RGB FOV | 90°×60°±3°; 120°×80°±3° (Lite version: no RGB) | 61°×90°±3° |
| Range | 0.3–8m (90% reflectivity) / 0.3–3m (5% reflectivity) | 0.3–17m (90% reflectivity) / 0.3–13m (10% reflectivity) |
| Accuracy | ≤3 cm | ≤3 cm |
| Average power consumption | ≤4W | ≤7W |
| Dimensions[1] | 80×37×25 mm | 92×47×51 mm |
| Weight | 190g | 460g |
| Power supply | 12V–28V DC | 24V DC |
| Communication interface | Ethernet/GMSL[2]/IO[3] | Ethernet/IO |
| Protection rating | IP54 | IP67 |
| Operating temperature | -20°C ~ 60°C | -20°C ~ 60°C |
| Storage temperature | -40°C ~ 85°C | -40°C ~ 85°C |
| Time synchronization | PTP | PTP |
| Software environment | C/C++/ROS SDK | C/C++/ROS SDK |
| OS support | Windows 7/8/10/11, Linux, Arm Linux/ROS | Windows 7/8/10/11, Linux, Arm Linux/ROS |
| Ambient light immunity | 100 kLux | 100 kLux |

[1] Refer to 3D models for exact dimensions. [2] GMSL version available upon request. [3] IO cable included with S10 Lite 120° only.

## Interface Definitions

### Camera Ports

Three interfaces are available: 24V DC power, 100M Ethernet, and an 8-pin functional IO port.

![S10 Interface (without IO)](https://i.ibb.co/Vn4ZC0B/9e7599ba-26bf-4ad3-a464-091a45901a71.png)

*S10 series interface diagram (without IO cable, except S10 Lite 120°)*

![S10 Lite Interface (with IO)](https://i.ibb.co/5gdZjLPB/b39797ff-9631-472d-805d-8081db53325f.png)

*S10 Lite 120° interface diagram (with IO cable)*

### IO Wiring

| Interface | Type | Notes |
|-----------|------|-------|
| IN1 | Input | Discrete input, active high, supports 24V/open |
| IN2 | Input | Discrete input, active high, supports 24V/open |
| OUT1 | Output | Discrete output, ground/open signal, supports 24V pull-up |
| OUT2 | Output | Discrete output, ground/open signal, supports 24V pull-up |
| COM | GND | Common ground for discrete outputs. IN1 paired with IN_COM1 |

### Wire Sequence

![Wiring Diagram 1](https://i.ibb.co/XffggLmY/134d66e9-925a-400e-8dc6-8fa1a64d0b7a.png)

![Wiring Diagram 2](https://i.ibb.co/d0CTMfFb/cff5a274-d65f-46a9-9971-fccf3cce04d4.png)

| Pin | Wire Color | Incorrect Definition | Correct Definition |
|-----|------------|---------------------|-------------------|
| 1 | Orange | OUT_COM2 | IN1 |
| 2 | Yellow | OUT_2 | IN_COM1 |
| 3 | Green | OUT_COM1 | IN2 |
| 4 | Purple | IN_COM2 | OUT_1 |
| 5 | Gray | IN2 | OUT_COM1 |
| 6 | Blue | OUT_1 | IN_COM2 |
| 7 | Brown | IN_COM1 | OUT_2 |
| 8 | White | IN1 | OUT_COM2 |

### Component Overview

![Component Diagram](https://i.ibb.co/ndNmTF5/678f115e-fb04-4c27-b4ba-043b2f70642b.png)

| Component | Description |
|-----------|-------------|
| VCSEL | Laser emitter |
| SPAD | Single-photon avalanche diode |
| RGB | RGB module |
| Power indicator | Slow flash when powered on |

## Integration Guide

### Mechanical Design

**1. S10 120°×80° FOV (3D diagram)**

![120° 3D](https://i.ibb.co/hxn75YS9/2ca196e6-0376-44f1-bef4-880d96ee3c4c.png)

**2. S10 90°×60° FOV (3D diagram)**

![90° 3D](https://i.ibb.co/2LhRYYt/f39ae392-7d6f-4a7c-af2a-439432dffd95.png)

**3. S10 120°×80° FOV (2D diagram)**

![120° 2D](https://i.ibb.co/B00qjZY/62643569-d92e-4a53-8d60-27d49be120d3.png)

**4. S10 FOV (2D diagram)**

![FOV 2D](https://i.ibb.co/Y7KvBSQd/329dfcaa-c023-4bc0-8fbe-8aa7065a08ec.png)

**5. Dimensions**

![S10 Dimensions](https://i.ibb.co/RTpxRtmz/2facf108-555e-403a-89ba-fdb6b2295ebc.png)

*S10 dimensional drawing*

![S10Pro Dimensions](https://i.ibb.co/jPbmXrFW/ca799406-382c-415b-b3aa-d248d20688c0.png)

*S10Pro dimensional drawing*

### Critical Installation Requirements

When installing the camera, ensure the **clearance zone (shown in pink)** remains completely unobstructed. Any object intrusion within this zone will directly interfere with point cloud data, causing image noise, false obstacle detection, or data anomalies.

![Clearance Zone 1](https://i.ibb.co/PZGfVMHn/026b4729-8b2c-495e-a08b-a4e910ff3370.png)

![Clearance Zone 2](https://120.26.180.177:2443/static-file/f33f58ae-4960-44c8-b866-0d66ba1d96b1/4829801b-defe-4a2e-af41-5daf5a7b557d.png)

The following images show typical incorrect installation examples where objects intrude into the clearance zone. These configurations violate installation specifications and cause point cloud interference, noise anomalies, and false obstacle detection. Avoid these configurations strictly.

![Incorrect Installation 1](https://i.ibb.co/nNMvLRPS/3d53cbd4-11a7-4cf6-9497-f5956a1c862c.png)

![Incorrect Installation 2](https://i.ibb.co/PvK5NJG2/1760a0e5-bb95-46d1-9310-07036f50bee1.png)

Improper installation environments can interfere with Time-of-Flight measurement principles, causing operational failures:

**1. Physical Obstruction and FOV Truncation**

Structural frames, ribs, or components intruding into the sensor's nominal FOV, or eccentric mounting with undersized openings, cause FOV cropping. The sensor may misidentify structural elements as targets. Symptoms include fixed blind zones, false short-range measurements, and compressed FOV, leading to missed obstacle detection and path planning errors.

**2. Near-Field IR Interference and Reflection**

The most common failure cause in confined installations involves abnormal IR reflection:

- **Multi-path interference**: IR light reflecting multiple times from structural walls alters detection timing, causing distance calculation errors.
- **Specular reflection**: Highly reflective smooth surfaces (polished metal, mirrors) cause mirror-like reflections, resulting in localized signal loss or saturation.
- **Highlight contamination**: When the sensor is <10cm from bright, smooth structural elements, strong reflections cause receiver saturation. This phase disturbance prevents ToF calculation, causes data distortion, accelerates receiver aging, and impairs core functionality.

**3. Optical Window Interference**

Protective glass or optical windows in front of the sensor can cause interference:

- **Multi-reflection artifacts**: Reflections from window surfaces create ghost images mixed with valid signals, causing depth map doubling and flying pixels.
- **Contamination and fogging**: Enclosed spaces promote fogging and dust accumulation on windows, reducing signal-to-noise ratio.
- **Material mismatch**: Standard glass or acrylic may block signals entirely, causing complete data loss. Use high-transmission optical glass instead.

**4. Other Hidden Factors**

- **Mounting stress**: Excessive clamping force causes lens deformation and optical axis offset, creating distance measurement errors in ToF cameras.
- **Thermal interference**: Poor heat dissipation in enclosed spaces causes sensor temperature rise and window thermal deformation, leading to ranging drift and long-term failure.

### Software SDK

Refer to the MRDVS Host Computer Software Manual and SDK Development Guide.

## Operating Specifications

| Item | Specification |
|------|---------------|
| **Operating Environment** | Temperature: -20°C ~ 60°C |
| | Illumination: 0–100 kLux |
| **Storage Environment** | Temperature: -40°C ~ 85°C |
| | Humidity: Max 90% RH |
| **Normal Operating Temperature Rise** | Housing temperature rise <25°C |
| **ESD Rating** | Contact discharge ±4KV, air discharge ±8KV |
| **RE Rating** | Compliant with GB 9254 Class A |
| **Operating Life** | 3 years |
| **Environmental Compliance** | RoHS |

## Quick Start Guide

### Connection and Testing

![Connection Diagram](https://i.ibb.co/W4y6Npp0/84ce70a3-9bfd-46d9-961d-a4d57091a8cb.png)

*Connection diagram*

### Power Supply

- Connect the DC power cable to the camera's DC power port and to a DC power adapter.
- Check the power indicator. Slow blue flashing indicates normal power-on status.
- If the indicator remains off or shows abnormal status (e.g., solid red), verify the power connection and adapter functionality.

### Network Configuration

- Connect the camera's communication port directly to the computer using a Cat6 Ethernet cable.
- Default IP address: 192.168.100.82.
- Configure the computer IP to the same subnet and disable the firewall.

### Software Operation

- Launch the host computer software to acquire camera images. Verify image clarity and absence of artifacts or lag to confirm proper connection.
- Refer to the Interface section below or the LxCameraViewer Host Computer Software Manual for detailed instructions.
- Contact MRDVS sales or technical support for additional assistance.

## Interface Overview

LxCameraViewer host computer software supports multiple device connections and viewing. It displays depth maps, amplitude maps, point clouds, and RGB output. The software enables reading and setting camera parameters and algorithm configurations. Users can view and save image data, camera configurations, and algorithm details.

The interface consists of three main areas: the device list (blue zone 1), menu bar (green zone 2), and image display (red zone 4). Double-click the menu bar to maximize/minimize; drag by holding the left mouse button.

![Interface Closed](https://i.ibb.co/dsqnWGL8/e6945a49-8ace-487b-a38c-793ff8bfbf99.png)

*Interface overview (camera closed)*

After opening a camera, the right-side function panel (zone 3) appears. Click "Basic Tools," "Applied Algorithms," or "Others" menus to access features. Basic tools include image display, 2D/3D settings, and filtering.

![Interface Open](https://i.ibb.co/nMDnbK6q/21260dfa-61bc-493e-843c-f5d8cd8c2fdc.png)

*Interface overview (camera open)*

The device list is located at the upper left. Click **[Open]** or **[Close]** to control the camera. The middle-left panel displays camera info, software operations, operation results, and streaming status. Device information appears at the lower left, showing details for the selected device.

Click **[Stream]** to start/stop image acquisition. The button disables during operation until completion. Click **[Single Capture]** to save images from active streams. Check **[Depth]**, **[Amplitude]**, **[RGB]**, or **[Point Cloud]** boxes to enable corresponding image formats.

For detailed information, refer to the LxCameraViewer Host Computer Software Manual.

## Laser Safety Classification

![Laser Safety](https://i.ibb.co/WWVvMD6y/bb91c636-2599-4b15-9b8a-0bcc833dcedd.png)

## Troubleshooting

| Issue | Solution |
|-------|----------|
| No data after opening camera in host computer software | Check firewall status (must be disabled); verify same subnet IP configuration; check network switch; try different computer; configure multi-subnet if needed |
| Host computer software detects multiple IP addresses | IP conflict detected on network. Manually select the correct IP address to open the camera |
| Software installation location | Default installation to C: drive may cause permission issues. Select a directory with appropriate read/write permissions |
| Poor edge accuracy on nearby white objects | Enable glare suppression algorithm (note: may reduce detection of black objects) |
| Large-area overexposure on retroreflective pillars | Enable glare suppression algorithm |
| Camera software displays no image or very small depth map | Update host computer software to Lanxin-MRDVS-1.3.66.0606 or later |
| Exclusive application permission failed | Ensure only one user connects to the camera at a time (versions 2.4.50.0720+ support multi-user permissions) |
| Sparse or missing object imaging | Check high exposure parameters (typically 600–1200); check low signal threshold (typically 10–30) |

## dToF vs. iToF Technology Comparison

dToF (direct Time-of-Flight) and iToF (indirect Time-of-Flight) each offer distinct advantages. dToF excels in fast ranging and interference resistance, making it ideal for mid-to-long-range complex scenarios. iToF performs exceptionally in high-precision close-range recognition within 5m. MRDVS leverages both technologies to provide precise, efficient distance perception solutions for diverse scenarios.

## Certifications

### S10

**CE EMC Certificate** (TÜV):
[CN25KQE6_001_cert_extsigned.pdf](https://120.26.180.177:2443/static-file/ab48162e-90f6-4fa5-b89c-d88fade3a9ff/7b5dacbd-bae8-4f87-ab13-b91e0a3912cb.pdf)

**EMC Test Report** (TÜV):
[S10_Reach_168576959a001-S10-reach.pdf](https://120.26.180.177:2443/static-file/a7b4c3a9-fd12-4982-8d0c-6dcffe26330b/f41529ce-8ae9-4533-b974-29b75f5a1e9d.pdf)

**RoHS Test Report**:
[S10_ROHS_report-MRDVS_25.07.pdf](https://120.26.180.177:2443/static-file/0b044bcd-51a7-4555-8a48-ec837b1feaba/bb04c5d3-f0de-4578-9a28-ffa766df2860.pdf)

**Test Report** (Zhejiang Institute of Quality and Metrology):
[S10_ClassI_XZJHW-20251050010_Eagle-S10camera.pdf](https://120.26.180.177:2443/static-file/14ed09f8-6520-48c4-ad3a-2baf96dc9aee/49c338ef-ddec-4140-abbd-04dc6abb6fdb.pdf)