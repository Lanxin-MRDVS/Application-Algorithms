## Product Overview

The MRDVS M4-G is an iToF-based RGB-D camera designed for close-range, high-precision environmental perception of embodied humanoid robots, featuring a GMSL2 interface. Its core capability is real-time depth perception at up to 4 mm accuracy within a 0.05–1 m range, synchronously outputting depth data and high-quality RGB images (1080P) at 30 FPS. It provides fine-grained 3D perception for close-range robot sensing, tabletop object grasping, and dexterous manipulation.

![](https://hub.mrdvs.cn/static-file/0c305d49-25f8-4018-9ef2-c65a21cac289/0e5b76fc-5a62-461f-a3fb-6bcd0b2f8ec7.jpg)

## Key Features and Applications

- **Accurate Depth Perception:** Uses ToF depth sensing technology. Compared to stereo matching and speckle pattern methods, it offers higher precision and better detail reproduction.
- **Excellent Low-Light Performance:** Active illumination ensures high-quality data in night-time or low-light environments.
- **Reduced Data Holes:** The active light solution effectively minimizes data voids and improves depth data completeness.
- **Multiple Output Formats:** Supports synchronous multi-data output. Simultaneously acquire depth maps, RGB images, and RGB alignment.
- **Long-Distance Anti-Interference:** Equipped with a GMSL2 interface, offering superior long-distance transmission capability and interference immunity compared to USB, ensuring stable data transfer.

**Primary Applications:**

This product is applied at the wrist of humanoid robots (VLA) for tabletop object grasping and dexterous manipulation in industrial scenarios.

- **Tabletop Object Grasping:** Humanoid robots autonomously identify and grasp various items in desktop environments, suitable for household service and office assistance scenarios.
- **Dexterous Manipulation:** In industrial settings, humanoid robots achieve part identification, grasping, and assembly through high-precision vision guidance, such as random bin picking, precision assembly, and machine tending.

## Specifications

| Parameter | MRDVS M4-G |
| :--- | :--- |
| Principle | iToF |
| Output Format | Depth & RGB & Point Cloud |
| ToF Resolution / Frame Rate | 640 × 480 (VGA), typical: 30 fps |
| ToF FOV | 90° × 70° (±3°) |
| RGB Resolution / Frame Rate | 1280 × 1056, typical: 30 fps |
| RGB FOV | 115° × 100° (±3°) |
| RGB Pixel Size | 2.5 µm |
| RGB ISP | Integrated |
| RGB HDR | ≥ 100 dB |
| RGB Lens Aperture (F#) | 2.05 |
| RGB Effective Focal Length (EFL) | 1.28 mm |
| Range | 0.05 m ~ 1 m |
| Range Accuracy | 1% (up to 4 mm @ 1 m) |
| Power Consumption | 3 W |
| Laser Wavelength | 940 nm |
| Dimensions | 60 × 30 × 29 mm |
| Weight | < 200 g |
| Power Supply | 12 V DC / 1 A |
| Communication Interface | SerDes |
| Protection Rating | IP54 |
| Operating Temperature | -20°C ~ 60°C |
| Storage Temperature | -40°C ~ 85°C |
| Software Environment | C/C++/ROS SDK |
| OS Support | Windows 7+, Linux, Arm Linux / ROS |
| Cooling | Passive |
| Eye Safety | Class I |

## Product Structure and Software

### Mechanical Dimensions

![](https://hub.mrdvs.cn/static-file/40ea8153-cd48-468c-8c89-8fc2e3d775e1/953b2c43-da9e-4805-87b7-0867304253ac.png "Figure 1. M4-G 3D Camera Mechanical Dimensions")

### Software SDK

Refer to the MRDVS host software user manual and the SDK development guide.

## Hardware Interface (GMSL Deserialization)

### Serializer Configuration

| Serializer | |
| :--- | :--- |
| Model | MAX96717 |
| I2C Address | 0x40 (7-bit) |
| GMSL Rate | GMSL2 (6 Gbps) |
| Mode | Pixel Mode |
| Frame Sync | Controlled by MAX96717 MFP0 |

### Sensor Parameters

| Sensor Info | |
| :--- | :--- |
| ToF Resolution | 2560 × 960 (raw8) |
| Data Type | 0x2A |
| ToF I2C Address | FPGA Forwarding |
| Virtual Channel | VC0 |
| RGB Resolution | 1280 × 1080 (YUV422 8-bit) |
| Data Type | 0x1E |
| RGB I2C Address | FPGA Forwarding |
| Virtual Channel | VC1 |

### FPGA Configuration

| FPGA | |
| :--- | :--- |
| I2C Address | 0x11 (7-bit) |
| MIPI | 4-lane, 1.2 Gbps |

## Prerequisites for Image Capture

### Trigger Signal

Per the MAX96717 manual, pair with a deserializer for hardware triggering (e.g., MAX96724).

![](https://hub.mrdvs.cn/static-file/941f3e6f-8eb5-4b57-81a2-8f6ca90d32be/e7a99ea7-43eb-46b5-b7bb-f7fbea7b0e55.png "Figure 2. MAX96724/F/R Frame Sync Signal Transmission Mechanism")

For GPIO-simulated trigger on MFP0 inside the MAX96717, refer to `trig.c`.

### Stream Start Command

```bash
i2ctransfer -f -y 4 w3@0x11 0x20 0x00 1
```

- `0x2000`: `0` = stop stream, `1` = start stream.
- `0x11` is the FPGA address.

## Integration Guide

| Item | | Specification |
| :--- | :--- | :--- |
| Operating Environment | Temperature | -20°C ~ 60°C |
| | Illuminance | 0 kLux ~ 100 kLux |
| Storage Environment | Temperature | -40°C ~ 85°C |
| | Humidity | Max 90% RH |
| Normal Operating Temperature Rise | | Housing temperature rise < 25°C |
| ESD Rating | | Contact discharge ±4 kV, air discharge ±8 kV |
| RE Rating | | Compliant with GB 9254 Class A |
| Service Life | | 10 years |
| Environmental Certification | | RoHS |
