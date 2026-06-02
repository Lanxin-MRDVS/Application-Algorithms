![V2Pro](https://i.ibb.co/GQfR69K4/01.webp)
## 1. Product Overview

### 1.1 Introduction

The MRDVS V2Pro is a second-generation high-performance navigation controller designed for complex environments. Building on the first-generation platform, this controller delivers substantial hardware upgrades by integrating top-view visual SLAM with 2D LiDAR to meet demanding navigation requirements in challenging scenarios. 

With onboard computing power eliminating the need for external industrial PCs, the V2Pro enables mobile robots to autonomously scan environments using its built-in 3D camera. The AI-powered mapping algorithm rapidly generates high-precision maps, providing stable and reliable navigation solutions for mobile robotics applications.

### 1.2 Key Features

#### 1.2.1 Precision Navigation for Mobile Robots

- **Multi-sensor fusion**: Combines a wide-angle top-view camera (108°×57°) with high-precision 2D LiDAR (270° scanning) and industrial-grade IMU to achieve ±1cm repeat positioning accuracy.
- **Edge computing**: 6 TOPS processor enables rapid high-precision map construction with one-click mapping through an intuitive visual interface, significantly reducing deployment complexity.

#### 1.2.2 Manual Forklift Enhancement Solution

- **WiFi 6 connectivity**: Next-generation wireless technology optimized for manual forklift positioning requirements, ensuring real-time data transmission reliability.
- **Audio alerts**: Built-in 3-pin audio output supports voice prompts and warning signals, enhancing safety in human-machine collaborative environments.

### 1.3 Applications

- **Facility logistics**: Supports seamless indoor/outdoor AGV and autonomous forklift navigation (warehouse to dock to production floor).
- **Forklift upgrade**: Replaces UWB solutions with higher accuracy (<3cm positioning), lower deployment costs, and faster installation.

![Application Scenario](https://i.ibb.co/6R91P0Hs/02.webp)

---

## 2. Specifications

### 2.1 Technical Specifications

| Component | Parameter | V2Pro Controller |
|-----------|-----------|------------------|
| **Top-view Camera** | Operating Range | 1m–15m (ambient light 0–10 klux) |
| | Field of View (FOV) | 108°(H)×57°(V)±3° |
| | Frame Rate | 20 fps |
| | Anti-interference | Glare-resistant, ambient light resistant |
| | Integrated Module | IMU (Inertial Measurement Unit) |
| **2D LiDAR** | Scan Frequency | 15Hz–25Hz (switchable) |
| | Detection Range | 15m @ 10% reflectivity / 40m @ 90% reflectivity |
| | Ranging Accuracy | ±30mm (typical) |
| | Angular Resolution | 0.1° |
| | Horizontal FOV | 270° |
| **Main Controller** | Processor | Rockchip 8-core ARM platform |
| | NPU Computing Power | 6 TOPS |
| | Communication Interfaces | 1× Ethernet / 1× CAN / 4× IO (2 IN, 2 OUT) |
| | Power Input | 24V(±4.8V) DC |
| | Power Consumption | 6.6W (average) / 15.3W (peak) |
| | Wireless Module | WiFi 6 |
| | Audio Output | 1×3-pin audio_out (L/R/GND) |
| | Dimensions | 146.5mm×66.3mm×89.4mm |
| | Protection Rating | IP54 |
| | Operating Temperature | -20°C ~ 60°C |
| | Storage Temperature | -40°C ~ 80°C |

*Note: Refer to 3D models for exact product dimensions.*

### 2.2 Interface Definitions

The controller features three main interfaces: 24V DC power input and two Fast Ethernet ports (one for AGV connection, one reserved for LiDAR).

![Interface Diagram](https://i.ibb.co/4ZhmQ255/e9bb4b68-b23a-45f3-873c-54beb31f17dc.webp)

| Port | Definition | Description |
|------|------------|-------------|
| CN6 | Ethernet | RJ45 female connector |
| CN7 | CAN Interface | Pink: CAN_H; Purple: CAN_L; Black: GND |
| CN8 | I/O Interface | 1: IN1+<br>2: IN1-<br>3: IN2+<br>4: IN2-<br>5: OUT1+<br>6: OUT1-<br>7: OUT2+<br>8: OUT2-<br>IO IN: 5-24V high valid<br>IO OUT: Push-pull output, supports 24V/100mA drive capability |
| CN9 | Power Interface | DC 24V/3A; 1: Positive; G: Negative |
| CN10 | Audio Output | 3.5mm male connector |

---

## 3. Product Information

### 3.1 Exterior View

![Product Exterior](https://i.ibb.co/Kc0xZj0H/7894c8cf-c5a1-4487-9e9a-36c124d61a44.webp)

### 3.2 Mechanical Drawings

![Mechanical Drawing](https://i.ibb.co/v6n1qGfc/2995c2d9-0f15-470f-9b6b-fb7a33801f88.webp)

### 3.3 Component Overview

#### 3.3.1 Component Layout

![Component Layout 1](https://i.ibb.co/RGcwM3Yk/3bdebbaf-423e-4d4c-ad57-cd7f79d13fac.webp)

![Component Layout 2](https://i.ibb.co/yn4GMJty/d9214987-b9ca-4c74-bad1-447b000d1391.webp)

| Item | Component |
|------|-----------|
| 1 | 2D LiDAR emission window |
| 2 | Top-view camera lens window |
| 3 | Top-view camera fill light |
| 4 | WiFi antenna interface |
| 5 | Mounting holes: 4-M3 screw holes |
| 6 | Camera cable (Ethernet, power, CAN, I/O, audio) |
| 7 | Nameplate label position |

#### 3.3.2 WiFi Communication Module

The V2Pro features a wireless network card providing stable, high-speed WiFi connectivity. Supporting MU-MIMO (Multi-User Multiple-Input Multiple-Output) technology, the module enhances channel capacity when multiple devices share the same frequency band. Dual-stream technology achieves transmission speeds up to 1200 Mbps. The card supports IEEE 802.11ax/ac/a/b/g/n standards in the ISM 2.400 GHz–2.4835 GHz band.

| Parameter Category | Details |
|-------------------|---------|
| Standards | IEEE 802.11ax/ac/a/b/g/n (2T2R)<br>Bluetooth: V5.3, V5.0, V4.2, V4.1, V4.0 LE, V3.0+HS, V2.1+EDR |
| Data Rates | **WiFi**:<br>• 802.11b: 11 Mbps<br>• 802.11a/g: 54 Mbps<br>• 802.11n: MCS0–15<br>• 802.11ac: MCS0–9<br>• 802.11ax: HE0–11<br>**Bluetooth**: 1 Mbps, 2 Mbps, up to 3 Mbps |
| Operating Frequency | IEEE 802.11ax/ac/a/b/g/n<br>ISM band: 2.400 GHz ~ 2.4835 GHz<br>(5G band not supported per local regulations) |

---

## 4. Integration Guide

### 4.1 Detection Range and Coordinate System

![Coordinate System](https://i.ibb.co/v6L0t04k/ec831dfa-3279-4408-904d-f783954ed032.webp)

### 4.2 Mounting Options

![Mounting Options](https://i.ibb.co/NgthMGzB/9fc8553e-939d-42d6-a472-e30ec7889b9b.webp)

### 4.3 Software SDK

Refer to the MRDVS Host Computer Manual and MRDVS SDK Development Guide.

---

### 4.4 Environmental and Reliability Specifications

| Item | Specification |
|------|---------------|
| **Operating Environment** | Temperature: -20°C ~ 60°C |
| | Illumination: 0–50 klux |
| **Storage Environment** | Temperature: -40°C ~ 85°C |
| | Humidity: Max 90% RH |
| **Normal Operating Temperature Rise** | Housing temperature rise <25°C |
| **ESD Rating** | Contact discharge ±4KV, air discharge ±8KV |
| **RE Rating** | Compliant with GB 9254 Class A |
| **Operating Life** | 3+ years |
| **Environmental Compliance** | RoHS |

---

## 5. Quick Start Guide

### 5.1 Package Contents

| Item | Description |
|------|-------------|
| 1 | V2Pro controller unit |
| 2 | 2-pin power cable |

### 5.2 Connection and Testing

![Connection Diagram](https://i.ibb.co/Gy7jdFM/9d8858e6-85a0-492f-a353-4e5adf1f81a2.webp)

#### 5.2.1 Power Supply

- Connect the DC power cable to the controller's DC power port and to a 24V/3A DC power adapter.
- Check the power indicator. Slow blue flashing indicates normal power-on status.
- If the indicator remains off or shows abnormal status (e.g., solid red), verify the power connection and adapter functionality.

#### 5.2.2 Network Configuration

- Connect the controller's communication port directly to the computer using a Cat6 Ethernet cable.
- Default IP address: 192.168.100.201.
- Configure the computer IP to the same subnet and disable the firewall.
- Access the web interface at 192.168.100.201:9998 (no password required).

#### 5.2.3 Software Operation

- Launch the host computer to acquire camera images. Verify image clarity and absence of artifacts or lag to confirm proper connection.
- Refer to section 5.3 or the LxCameraViewer Host Computer Manual for detailed operation instructions.

Contact MRDVS sales or technical support for additional assistance.

### 5.3 Interface Overview

![Software Interface](https://i.ibb.co/5h2L3y0x/69362392-66e2-4bd2-8fc3-72e4a3e1efbe.webp)

1. **Red menu bar**: Access function details (start mapping, relocalization, map management).
2. **Blue area**: Displays loaded 2D contour maps and robot positioning icons.
3. **Green area**: Real-time RGB feed from top-view camera.
4. **Yellow area**: Real-time relocalization signal strength (green: excellent, blue: good, red: weak); current robot coordinates, velocity, and mouse position coordinates.

### 5.4 Mapping Procedure

**1. Start Mapping**

![Start Mapping](https://i.ibb.co/mC10gdRw/8cdd9468-9cb7-437d-a823-4a0cbffae053.webp)

**2. Enter Map Name**

- Map names must consist of letters, numbers, and underscores only. Cannot begin with a number.

**3. Mapping Interface**

![Mapping Interface](https://i.ibb.co/q4w9LNN/12edb330-0198-49f8-a1de-cbcc05192b4a.webp)

- During mapping, maintain robot speed below 0.5 m/s and angular velocity below 20°/s.
- The interface displays LiDAR contours and top-view camera feed.

**4. Path Planning**

Plan mapping routes in advance. Maintain low speed (<0.2 m/s), constant velocity, straight-line motion, and 90-degree turns. Avoid duplicate paths and random movements. Maintain approximately 1/3 overlap between parallel passes (typically 2m spacing) to maximize coverage of the mapping area or robot path.

![Ideal Path Pattern](https://i.ibb.co/D3mDScW/045b2eb3-7aca-4ae2-8693-660381d3301e.webp)

**5. Complete Mapping**

- After scanning the operational area, click "End Mapping" in the menu bar. Wait for processing to complete (duration depends on scanning area size).

### 5.5 Map Management

**1. Map Management Interface**

**2. Backend Maps**

![Backend Maps](https://i.ibb.co/gb0rv8tg/82af1a8d-d514-4304-89d0-439e413314b3.webp)

After mapping completion, access the map management interface to view created maps in the backend list. Click "Deploy" to transfer maps to the host. Deploy all required maps. Supports map modification, export, and deletion.

**3. Host Maps**

![Host Maps](https://i.ibb.co/ZnS8xVH/60add4a5-7fb8-403b-89fa-52c52a02ac2f.webp)

Click "Apply" in the host maps section to activate a map. Supports map export and deletion. **Important**: Restart the controller after applying a map for changes to take effect. Failure to restart may result in relocalization failure.

### 5.6 Relocalization

![Relocalization](https://i.ibb.co/BFwDbL0/deb0504b-1722-4266-9085-373b38eaf7b1.webp)

- Click "Relocalization" and drag with the mouse to set an approximate pose using LiDAR point cloud and contour matching hints.
- Upon successful relocalization, positioning timeout warnings disappear.

### 5.7 Parameter Configuration

![Parameter Configuration](https://i.ibb.co/5WSsPLND/edeb23b6-0f47-4be5-8d33-26a5b0a8a1f5.webp)

View and configure chassis positioning parameters and sensor calibration values including LiDAR-to-camera extrinsic parameters.

---

## 6. Troubleshooting

| Issue | Solution |
|-------|----------|
| Camera does not respond when clicked | Check and disable firewall settings to ensure communication is not blocked |
| Host computer detects multiple IP addresses | IP conflict detected on network. Manually select the correct IP address to open the camera |
| Unstable data stream after opening camera | Use Gigabit Ethernet cable. Fast Ethernet cables may cause initial data transmission instability |
| Software installation location issues | Default installation to C: drive may cause permission issues. Select a directory with appropriate read/write permissions |

---

## 7. Safety Information

### 7.1 Laser Safety

![Laser Warning](https://i.ibb.co/Z6Cct1qX/12994efb-680e-499f-bce2-781956a9edf9.webp)

### 7.2 Lithium Battery Warning

![Battery Warning](https://i.ibb.co/S4Ljjrnq/244bbbe8-7ff8-4f38-a9c2-4b13fe44e7d2.webp)