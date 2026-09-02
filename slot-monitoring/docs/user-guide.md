# Slot Monitoring User Guide

[Documentation Home](../../README.md) / [Slot Monitoring](../README.md) / User Guide

> **Delivery note:** This guide describes the current camera-side workflow. Slot Monitoring is planned for AW3, but no verified public package is recorded in this repository yet.

Source last modified: March 4, 2025

## 1 Introduction

The MRDVS slot monitoring application is designed to monitor storage locations in warehousing and logistics. Its detection algorithm runs inside the camera and does not require an external industrial PC.

Users only need to perform camera extrinsic calibration and define multiple storage locations. A single camera can monitor 6–8 storage locations, and multiple cameras can be deployed in the same warehouse. The calibration results are generated automatically during extrinsic calibration.

This document describes how to deploy and use MRDVS slot monitoring for storage-location status and occupancy detection.

## 2 System Components

1. An M-, S-, or T-series depth camera and one set of storage location monitoring software.
2. A mid360 LiDAR, one set of storage location monitoring software, and an industrial PC.

## 3 Camera Hardware Deployment Guide

### 3.1 Supported Camera Types

| Camera type | M-/S-/T-series camera |
| --- | --- |
| Camera user manuals <br>M-Series ToF Camera<br>S-Series Obstacle-Avoidance Camera | ![Figure 3-1-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/3-1-1.png) |

### 3.2 LiDAR

| LiDAR type | mid360 |
| ---------- | ------ |

### 3.3 Camera Mounting

Secure the camera with a mounting bracket. The following figure shows a typical mounting arrangement and camera bracket.

![Figure 3-3-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/3-3-1.png)

### 3.4 Camera Connections

1. Power the camera with 24 VDC and connect it using a Category 6A or Category 7 Ethernet cable. After installation, open the storage location detection PC application on a laptop to perform camera extrinsic calibration and define the detection range. The algorithm then runs inside the camera in real time.
2. For a multi-camera deployment, connect the cameras through a Gigabit Ethernet switch. Mount each 3D vision camera securely at the height specified in the CAD layout. After mounting, connect the camera to a regulated 24 VDC power supply and use the appropriate Ethernet cable to connect it to the switch or main controller.
3. After completing the preparation, place goods in the storage locations within the camera's field of view and proceed with software deployment.

![Figure 3-4-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/3-4-1.png)

## 4 Camera Software Installation Guide

### 4.1 Installation Workflow

- For first-time use, complete the procedure shown below.

![Figure 4-1-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-1-1.png)

### 4.2 PC Requirements for the Storage Location Detection Application

The computer running the storage location detection PC application should meet the following requirements.

| Item | Requirement |
| --- | --- |
| Operating system | Windows 10 or later |
| CPU | Intel® Core™ i5, 7th generation or later, recommended |
| Memory | 8 GB or more |
| GPU | Intel(R) UHD Graphics, integrated graphics of equivalent performance, or better |

### 4.3 Installing the Camera PC Application

1. Download the camera PC application from the MRDVS knowledge base: [Software Download](https://zcnt5g3o2989.feishu.cn/wiki/Q8IYwGiGaiIvIyktiavczymanOe?from=from_copylink)

![Figure 4-3-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-3-1.png)

2. Double-click the installer to install the Lanxin-MRDVS PC application. Install the software on a drive other than drive C.

![Figure 4-3-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-3-2.png)

3. Select the language and click **OK**. Select an installation directory on a drive other than drive C, and then click **Next**.

![Figure 4-3-3](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-3-3.png)

4. Select **Create a desktop shortcut**, and then click **Next**.

![Figure 4-3-4](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-3-4.png)

5. Click **Install** to begin the installation.

![Figure 4-3-5](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-3-5.png)

6. After installation is complete, run the camera PC application.

![Figure 4-3-6](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-3-6.png)

### 4.4 Installing the Storage Location Detection PC Application

1. Copy the provided storage location detection PC application to `\Lanxin-MRDVS\Tools` under the camera PC application directory.

![Figure 4-4-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-4-1.png)

2. When prompted, select **Replace the files in the destination**.

![Figure 4-4-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-4-2.png)

3. Double-click the application to run it.
4. In the device list on the left, a camera status of **Unknown** indicates that the storage location detection algorithm is not installed on the camera.

![Figure 4-4-3](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-4-3.png)

### 4.5 Upgrading the Storage Location Detection Application

To upgrade the storage location detection application, replace only the `.exe` file.

### 4.6 Upgrading the Algorithm

1. To upgrade the camera algorithm, open the camera PC application and double-click **LxCameraViewer**.

![Figure 4-6-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-6-1.png)

2. Click **Open** to view the camera image.

![Figure 4-6-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-6-2.png)

3. Select Basic Tools → Function Settings → **Firmware Upgrade** to flash the storage location detection algorithm. Obtain the algorithm package from technical support.

![Figure 4-6-3](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-6-3.png)

4. Click **Execute**, select the storage location detection algorithm, and click **Open** to begin flashing the algorithm.

![Figure 4-6-4](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-6-4.png)

5. The camera restarts while the algorithm is being flashed, and its ID disappears temporarily from the device list. When the ID reappears, the flash operation has completed successfully.

![Figure 4-6-5](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-6-5.png)

6. Reopen the storage location detection application. The device is now shown in green in the device list.

![Figure 4-6-6](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/4-6-6.png)

## 5 Storage Location Detection Application Interface

### 5.1 Starting the Application

1. Double-click **LxApplicationViewer.exe** to start the storage location detection application. In the device list on the left, click an online camera to open its image.

![Figure 5-1-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/5-1-1.png)

2. Select Administrator as the current user. No password is required; click Confirm to enter administrator mode. User mode does not allow storage location detection parameters to be configured. Administrator mode provides the additional Storage Location Detection and Camera Configuration options.

![Figure 5-1-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/5-1-2.png)

### 5.2 Basic Tools

Basic Tools includes user switching, ideal ground plane, extrinsic-calibration ground plane, display cache, algorithm display, image export, history playback, and storage location status.

![Figure 5-2-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/5-2-1.png)

| Basic tool | Description |
| --- | --- |
| User switching | Switch permissions. User permission: view detection results only. Administrator permission: configure the camera and storage location detection parameters. |
| Ideal ground plane | Reference horizontal plane for the ground; can be hidden. |
| Extrinsic-calibration ground plane | Horizontal plane at the height determined by camera extrinsic calibration; can be hidden. |
| Display cache | No change is required. |
| Display algorithm | Shows the algorithm currently in use. |
| Export images | Exports stored images. |
| History playback | Displays RGB and ToF image logs. |
| Storage location detection results | Displays whether goods are present in each storage location. |

### 5.3 Global Configuration

Switch the camera operating mode.

![Figure 5-3-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/5-3-1.png)

### 5.4 Storage Location Detection

![Figure 5-4-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/5-4-1.png)

| Global setting | Description |
| --- | --- |
| Algorithm version | Current algorithm version. |
| AI filtering | Supports semantic segmentation; people can be segmented out and excluded from detection. |
| Detection frequency | Algorithm detection frequency. |
| Alignment angle | If the detected angle exceeds this value, the result is 2. Result 2 indicates that an object is present but its angle is outside the allowed range. Unit: degrees (°). |
| Alignment validation | When enabled, checks the current object's angular deviation and whether it extends beyond the defined detection area. |
| Temporal filtering | Filtering parameter; no change is required. |
| Minimum point count | An object is considered present only when its point-cloud count is greater than this value. |
| Save and write to camera | Saves the settings and writes them to the camera. |

![Figure 5-4-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/5-4-2.png)

| Storage location area setting | Description |
| --- | --- |
| Add storage location | Adds a storage location detection area. |
| Delete storage location | Deletes a storage location detection area. |
| Current box | Selects the current storage location detection area. |
| Minimum X | Minimum X coordinate of the detection box. |
| Maximum X | Maximum X coordinate of the detection box. |
| Minimum Y | Minimum Y coordinate of the detection box. |
| Maximum Y | Maximum Y coordinate of the detection box. |
| Minimum Z | Minimum Z coordinate of the detection box. |
| Maximum Z | Maximum Z coordinate of the detection box. |
| ID | Name of the detection box. When multiple detection areas are defined, assign distinct IDs to identify them. |
| Adjust area by dragging | Within the adjustment area, hold the left mouse button and drag to move the area in X and Y. Hold the right mouse button and drag to move the area in Z. |

![Figure 5-4-3](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/5-4-3.png)

| Advanced function — Copy storage location box | Description |
| --- | --- |
| Copy current box | Copies the selected storage location detection area. |
| Copy/translation instructions | Displays instructions for copying and translating an area. |
| Direction | Direction in which to copy the area: X, Y, or Z. |
| Spacing | Spacing between the source detection area and each copied area. |
| Quantity | Number of copied detection areas. |
| Execute | Creates multiple equally spaced copies of the detection area. |

| Advanced function — QR Code calibration | Description |
| --- | --- |
| QR Code calibration instructions | Displays QR Code calibration instructions. |
| X | Storage location width. |
| Y | Storage location length. |
| Z_MIN | Minimum depth of the storage location. |
| Z_MAX | Maximum depth of the storage location. |
| Calibrate | Creates the QR-calibrated storage location when clicked. |

### 5.5 Camera Configuration

![Figure 5-5-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/5-5-1.png)

| Camera setting | Description |
| --- | --- |
| Camera name | Changes the current camera name. Use distinct names to identify cameras in a multi-camera deployment. |
| Simulation mode | For internal use; users should leave this disabled. |
| Image logging mode | Enables algorithm image logging and stores image data inside the camera. |
| Image acquisition mode | MDS and SDK modes are available. MDS does not exclusively occupy the camera, so the camera PC application can still open it. SDK mode exclusively occupies the camera; while the algorithm is running, the PC application cannot open the camera. |
| x | Calibrated camera position on the X axis. |
| y | Calibrated camera position on the Y axis. |
| z | Calibrated camera height above the ground on the Z axis. |
| roll | Calibrated camera roll angle. |
| pitch | Calibrated camera pitch angle. |
| yaw | Calibrated camera yaw angle. |
| Ideal ground plane | Keep the default value. |
| Save and write to camera | After extrinsic calibration, click this button to save and apply the parameters; otherwise, the parameters do not take effect. |
| Read configuration from camera | Reads the current configuration parameters from the camera. |
| Extrinsic calibration | Calibrates the camera height above the ground and its roll, pitch, and yaw angles. |

### 5.6 Language

Switches between Chinese and English.

### 5.7 Status Bar

![Figure 5-7-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/5-7-1.png)

| Status bar item | Description |
| --- | --- |
| RGB | Select to display the RGB image. |
| Point cloud | Select to display the point-cloud image. |
| Stop algorithm | Stops the algorithm. The algorithm remains stopped until the camera is powered on again. |
| Upgrade firmware | Upgrades the algorithm firmware. |
| Restart camera | Restarts the camera. |

## 6 Storage Location Detection Deployment Procedure

When the application opens, it displays the RGB image by default. After switching to the point-cloud image, the display initially appears black. Move the pointer into the image area, scroll the mouse wheel, and drag with the left mouse button to display the point-cloud data.

![Figure 6-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-1.png)

![Figure 6-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-2.png)

### 6.1 Camera Network Configuration

1. The following procedure uses Windows 10 as an example. Double-click Control Panel.
2. In Control Panel, click **View network status and tasks**.

![Figure 6-1-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-1-1.png)

3. In Network and Sharing Center, click **Change adapter settings**.

![Figure 6-1-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-1-2.png)

4. In Network Connections, double-click the Ethernet adapter connected to the camera.

![Figure 6-1-3](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-1-3.png)

5. Check the Ethernet link status (a Gigabit Ethernet port is recommended), and then click **Properties**.

![Figure 6-1-4](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-1-4.png)

6. In Ethernet Properties, locate **Internet Protocol Version 4 (TCP/IPv4)** and double-click it.

![Figure 6-1-5](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-1-5.png)

7. Select **Use the following IP address**, and enter the IP address, subnet mask, and default gateway.

![Figure 6-1-6](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-1-6.png)

8. Set the IP address to `192.168.100.xxx`, the subnet mask to `255.255.255.0`, and the default gateway to `192.168.100.1`. After entering the settings as shown, click **OK**.

![Figure 6-1-7](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-1-7.png)

9. The previous dialog reappears. Click **OK** again to complete the network configuration.

![Figure 6-1-8](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-1-8.png)

### 6.2 Confirming That the Firewall Is Disabled

1. After securing the camera in place, begin deployment by disabling the computer firewall.
2. Using Windows 10 as an example, double-click **Control Panel**, and then click **System and Security**.

![Figure 6-2-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-2-1.png)

![Figure 6-2-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-2-2.png)

3. Click **Windows Defender Firewall**.

![Figure 6-2-3](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-2-3.png)

4. Click **Turn Windows Defender Firewall on or off**.

![Figure 6-2-4](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-2-4.png)

5. For both private and public networks, select **Turn off Windows Defender Firewall**, and then click **OK**.

![Figure 6-2-5](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-2-5.png)

### 6.3 Storage Location Detection — Extrinsic Calibration

1. After configuring the camera IP address and disabling the firewall, proceed to the second deployment step. Open the application and perform algorithm extrinsic calibration to determine the reference ground-plane position and camera mounting-angle deviation.
2. Click Camera Configuration to open the parameter calibration page. Before extrinsic calibration, verify that x, y, z, roll, pitch, and yaw are all 0. If any value is nonzero, reset all values to 0 and click **Save and write to camera**. After the parameters have been saved successfully, perform extrinsic calibration again.

![Figure 6-3-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-3-1.png)

3. After confirming that all parameters are 0, click **Extrinsic Calibration**. A message appears when calibration succeeds, and the calibrated camera parameters are shown in the parameter panel on the right.

![Figure 6-3-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-3-2.png)

4. For storage location detection, correct the calibrated pitch as follows: subtract 180° when pitch is positive, or add 180° when pitch is negative. After correction, the blue Z-axis arrow must point upward, and the ground X and Y axes must be parallel to the ground. For example, if the calibrated pitch is 1.695°, then `1.695° - 180° = -178.305°`. Enter `-178.305°` for pitch to invert the coordinate system.

![Figure 6-3-3](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-3-3.png)

5. Click **Save and write to camera**. After the calibration parameters are saved successfully, proceed to the storage location detection settings. **Important: The corrected pitch must be set; otherwise, the measured height will be inaccurate.**

![Figure 6-3-4](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-3-4.png)

### 6.4 Storage Location Detection — Global Settings

1. Click Storage Location Detection to open its settings. In Global Configuration, pay particular attention to Alignment Angle, Alignment Validation, and Minimum Point Count.
2. If object orientation is constrained, enable Alignment Validation and set the alignment angle. The software returns the corresponding result when the object angle exceeds this value: no object = 0; object present = 1; object present and angle exceeds the alignment angle = 2; object extends beyond the defined area = 3.
3. To ignore small objects or reduce false detections, set Minimum Point Count. This value is the number of points in the point cloud.
4. After completing the global configuration, click **Save and write to camera** to store the parameters in the camera.

![Figure 6-4-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-4-1.png)

### 6.5 Storage Location Configuration

1. To set the detection range, first switch to the top or bottom view when adjusting its length and width (X and Y). The following figure shows the view shortcuts.

![Figure 6-5-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-5-1.png)

2. Place a pallet within the field of view and click **Add storage location**. A new storage location and ID appear below Storage Location Configuration. The ID can be edited; in this example it is changed to “Storage Location Test 1.”

![Figure 6-5-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-5-2.png)

![Figure 6-5-3](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-5-3.png)

3. After clicking **Add storage location**, switch the point cloud to bottom view. Click the point-cloud image and press **X** to begin drawing the storage location area. The Add Storage Location button turns gray, indicating that an area can be drawn in the image. The **X** key starts and ends drawing: press it once to start and once again to finish.

![Figure 6-5-4](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-5-4.png)

4. Use the mouse wheel to zoom. Hold the left mouse button and draw a rectangle around the entire pallet, then release the button; the detection area is created automatically. Press **X** again to end area drawing. Adjust the minimum and maximum X, Y, and Z values to confirm the area dimensions. After the area is correct, always press **X** to end drawing; otherwise, the area may not be created successfully.

![Figure 6-5-5](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-5-5.png)

5. Use the keyboard shortcut to switch to bottom view. The red arrow indicates the X direction of the detection range. Scroll the mouse wheel to change the corresponding value and adjust the width. In this example, the X dimension is set slightly larger than the pallet width.

![Figure 6-5-6](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-5-6.png)

6. The green arrow indicates the Y direction. Scroll the mouse wheel to change the corresponding value and adjust the length. In this example, the Y dimension is set slightly larger than the pallet length.

![Figure 6-5-7](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-5-7.png)

7. The blue arrow indicates the Z direction. Scroll the mouse wheel or enter values directly. Set the minimum Z slightly above the ground to prevent the ground from being detected as an object. In this example, the maximum Z is 1500. Set the maximum height according to the object size. Points above the maximum Z are excluded from detection.

![Figure 6-5-8](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-5-8.png)

8. After configuring the detection area, click **Save and write to camera**. The parameters are stored in the camera, and detection can begin.

![Figure 6-5-9](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-5-9.png)

### 6.6 Storage Location Detection — Advanced Settings

#### 6.6.1 Advanced Function — Copying Storage Locations

1. Click **Copy/translation instructions** to display the relevant information. In an actual deployment, define the layout from the CAD drawing, draw one storage location area, and copy it to create the remaining areas instead of drawing each one manually.

![Figure 6-6-1-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-6-1-1.png)

2. In this example, Direction is X, Spacing is 10, and Quantity is 2. Click Execute; a confirmation message appears.

![Figure 6-6-1-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-6-1-2.png)

3. Click Yes. Two storage locations of the same size are created in the positive X direction with a spacing of 10. In the storage location list, `(0)` and `(1)` are appended to the source ID.

![Figure 6-6-1-3](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-6-1-3.png)

4. Next, set Direction to Y, Spacing to -40, and Quantity to 3. Click Execute to create three areas of the same size in the negative Y direction. IDs `(2)`, `(3)`, and `(4)` are added to the existing `(0)` and `(1)` entries.

![Figure 6-6-1-4](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-6-1-4.png)

5. After copying the storage locations, click **Save and write to camera**; otherwise, the parameters do not take effect.

#### 6.6.2 Advanced Function — QR Code Calibration

1. QR Code calibration simulates the actual deployment and automatically draws the storage location area. A QR calibration board of at least 1 m × 1 m is recommended. Click **QR Code calibration instructions** to display the calibration procedure.

![Figure 6-6-2-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-6-2-1.png)

2. Place the QR calibration board in the target area. Switch to the RGB image and ensure that the QR Code is visible.

![Figure 6-6-2-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-6-2-2.png)

3. Center the QR Code in the field of view, switch to the point-cloud image, and locate the **QR Code** calibration panel. Enter X (width), Y (length), Z_MIN (minimum depth), and Z_MAX (maximum depth) in advance.

![Figure 6-6-2-3](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-6-2-3.png)

4. Click **Calibrate**. The storage location is drawn automatically from the configured X, Y, and Z values and can be viewed in the Storage Location Configuration area. `QR_BOX` is the area created from the QR Code settings.

![Figure 6-6-2-4](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-6-2-4.png)

5. After QR Code calibration, click **Save and write to camera**; otherwise, the parameters do not take effect.

### 6.7 Viewing Detection Results

1. After completing extrinsic calibration, detection settings, and area configuration, click **Basic Tools** and place an object in the detection area. When no object is present, the storage location status panel shows that the area is empty.

![Figure 6-7-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-7-1.png)

2. After a pallet is placed in the area, the status panel shows that the storage location is occupied. `Result` at the bottom of the application is 1, indicating that goods are present.

![Figure 6-7-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-7-2.png)

3. When Alignment Validation is enabled, `Result` 2 indicates that a pallet is present but its angle is outside the allowed range.

![Figure 6-7-3](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-7-3.png)

4. When Alignment Validation is enabled, `Result` 3 indicates that a pallet is present but extends beyond the storage location detection area. The red box is the 0° detection area; the green box is the actual object point cloud.

![Figure 6-7-4](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-7-4.png)

### 6.8 Viewing Detection Logs

1. When a storage location status changes, click History Playback and select a timestamp on the left to view object changes within the effective field of view. The following example shows goods being removed.

![Figure 6-8-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-8-1.png)

![Figure 6-8-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-8-2.png)

### 6.9 Application Example

1. In this example, two detection areas are drawn to determine whether a pallet and goods are present. One area detects the pallet, and the other detects the goods.

![Figure 6-9-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-9-1.png)

2. Use `Result` to determine the goods status, including excessive angle or an object extending beyond the detection area. In the following example, Alignment Angle is 15°. When the object angle exceeds 15°, `Result` is 2, indicating excessive angular deviation.

![Figure 6-9-2](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-9-2.png)

![Figure 6-9-3](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-9-3.png)

3. With Alignment Angle set to 15°, place the object sideways so that it extends beyond the area. `Result` is 3, indicating that the object is outside the detection area.

![Figure 6-9-4](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/6-9-4.png)

## 7 Communication Protocols

### 7.1 TCP Communication

1. Detection results can be obtained over TCP. In a network debugging tool, set the remote camera IP address to `192.168.100.82` and the port to `14951`. Send `RESULT_UPDATE` to receive the storage location detection results.

![Figure 7-1-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/7-1-1.png)

### 7.2 UDP Communication

1. Detection results can be obtained over UDP. In a network debugging tool, set the remote camera IP address to `192.168.100.82` and the port to `14950`. Send `RESULT_UPDATE` to receive the storage location detection results.

![Figure 7-2-1](https://pub-7b25325ec91643989210e56dc1a181a4.r2.dev/storage_detection/assets/7-2-1.png)

### 7.3 HTTP Communication

1. Detection results can be obtained over HTTP on port `14952`.
2. The upper-level system (WMS) sends a request for results, and the vision system returns a JSON-formatted string.

| **WMS → vision system** |  |
| --- | --- |
| **Value** | **Meaning** |
| `RESULT_UPDATE` | Triggers the vision system to return results. |
| **Vision system → WMS** |  |
| **Field** | **Meaning** |
| `IP` | IP address of the source camera. |
| `SS` | Storage location status: 0 = empty; 1 = occupied. |
| `SS_DATA_TIME` | Time at which the storage location detection data was acquired. |
| `SS_RES_TIME` | Time at which the storage location detection result was output. |
| `nick_name` | Configurable storage location camera name. |
| `ret_code` | Return code: 0 = success. |

## 8 Appendix

```jsonc
{
  "IP": "192.168.100.82", // Camera IP address
  "SS": {
    "huowu-inspection": 0, // Status: 0 = empty, 1 = occupied; "huowu-inspection" is an area name
    "tuopaninspection": 1  // Status: 0 = empty, 1 = occupied; "tuopaninspection" is an area name
  },
  "SS_DATA_TIME": "2024_11_15_16_57_08.060", // Storage location data timestamp
  "SS_RES_TIME": "2024_11_15_16_57_08.748",  // Result timestamp
  "nick_name": "_default_",                  // Camera name
  "ret_code": 0                               // Return code: 0 = success
}
```
