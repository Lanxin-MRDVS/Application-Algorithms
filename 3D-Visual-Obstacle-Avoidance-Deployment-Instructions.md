**Version:**  1.1
**Author:** Junhao Shao, Ruiyang Liu    
**Date:** May 2026

---

## 1. Introduction

Visual obstacle avoidance is a system developed by MRDVS. Based on its self-developed S-series camera system using TOF-based RGBD cameras, it integrates deep learning and traditional 3D vision algorithms to create a precise, real-time obstacle avoidance system suitable for diverse scenarios. This system is configurable on a single device and can be used in multi-device collaboration, possessing a degree of initiative and predictive capability.


**Key Features:**
- Real-time dynamic detection & tracking
- Adaptive ground detection
- Support for multiple signal outputs (UDP, TCP, API, CAN, IO)
- Multi-device collaborative operation
- Five operational modes with predictive capabilities

---

## Application Examples

### 1. Autonomous Guided Vehicle (AGV)
As shown in Figure 1, the camera on the autonomous guided vehicle
is installed relatively low. It is recommended to use an S10 series camera and
install it on the front surface of the autonomous guided vehicle in the direction
of movement. When designing the structure, care must be taken to ensure an
unobstructed field of view.

<p align="center">
<img width="550" height="417" alt="Näyttökuva 2026-05-26 kello 16 00 29" src="https://github.com/user-attachments/assets/3d2ad932-317e-4baa-8dd2-10962eb381a9" />
<br>
  <em>Figure 1: Autonomous Guided Vehicle</em>
</p>

### 2. Forklift
For intelligent forklifts, the camera is installed at a higher position.
As shown in Figure 2, the intelligent forklift camera is installed at a relatively
high position. It is recommended to use an S10 series camera, mounted at a
30°-55° downward angle to the forklift mast, so that the edge of the camera’s
field of view is just above the front surface of the forklift. Furthermore, the
camera installation height should not exceed 2 meters.

<p align="center">
<img width="765" height="570" alt="Näyttökuva 2026-05-26 kello 16 00 40" src="https://github.com/user-attachments/assets/606cfd4a-86b8-4c1c-a69d-22e98878c710" />
<br>
  <em>Figure 2: Forklift</em>
</p>

---

## 2. Comparison between Obstacle avoidance 1.0 and Obstacle avoidance 2.0

### Core functions supported by both 1.0 and 2.0

The two algorithms share a same underlying architecture. They rely entirely on the camera's built-in computing power for localized processing, eliminating the need for external industrial PC resources. This lightweight design ensures real-time performance, making it perfectly suited for robot terminal. The universal features are as follows:

-  Point Cloud Coordinate Transformation: By applying calibrated extrinsic parameters, the raw point cloud data captured by the camera is accurately transformed into the robot's coordinate system. This eliminates perspective deviations caused by the camera angle and ensures precise obstacle positioning.

- Zone Intrusion Detection: Supports customizable detection zone models for obstacle avoidance, including rectangular bounding boxes and fan-shaped zones. These adaptable models cater to various operational scenarios such as straight-line navigation, turning, and wide-angle detection.

- Tiered Obstacle Avoidance Output signal: The system continuously monitors intrusion points within the target area in real time. Based on the detected obstacles, it outputs three levels of control signals via IO interfaces or other standard communication protocols. The unified signal definitions are:

     - 0: No obstacles detected; the robot proceeds normally.
     - 1: Minor/distant obstacle detected; the robot slows down.
     - 2: Close/proximity hazard detected; the robot executes an emergency stop.


### New Upgrades in Obstacle avoidance 2.0

The Obstacle Avoidance Algorithm 2.0 is fully backward-compatible with all core features of Version 1.0. To address the shortcomings of traditional point-cloud obstacle avoidance, which lacks clustering, object recognition, and scene adaptability, the version 2.0 introduces four major core functions, significantly enhancing the intelligence and safety of the robot's navigation.

- Non-Semantic Object Clustering Detection: Version 1.0 could only detect intruding point clouds in the Obstacle avoidance zone, but unable to consolidate whether its scattered or continuous points. This often led to false triggers from single noise point and blurred obstacle contours. Version 2.0 introduces a non-semantic clustering algorithm that automatically identifies and groups spatially connected obstacle point clouds within a target area. It autonomously clusters these points, filters out separated individual noise points, and accurately calculates the bounding box for each independent obstacle. By outputting precise position and size information, the robot can now not only sense that there is an obstacle but also clearly determine where it is and how large it is.

- DEMO-Level Ground Void Detection: Version 1.0 only supported the detection of protrusion obstacles and could not identify high-risk scenarios such as ground depressions, voids, or missing steps, posing safety issues during navigation. Version 2.0 introduces a ground integrity detection function (currently in DEMO stage). By analyzing point-cloud height difference features, it can accurately identify voids, deep pits, and depressed areas on the operating surface. When a high-risk void enters the detection zone, the system will automatically trigger an emergency stop (Signal 2). This addresses the limitation of traditional obstacle avoidance systems, which cannot defend against ground depression related dangers, making it highly suitable for outdoor operations and complex terrain scenarios.

- Customizable Semantic Obstacle Avoidance Feature: Version 2.0 introduces AI semantic recognition capabilities powered by neural networks, supporting the deployment of customized detection models. Based on specific operational requirements, users can train and load designated object recognition models to accurately distinguish between different types of obstacles, such as pedestrians, vehicles, equipment, walls, and miscellaneous items—enabling targeted obstacle avoidance.
Furthermore, the system can output precise bounding boxes for these semantically identified obstacles. This supports advanced strategies such as tiered obstacle avoidance and dynamic rerouting planning. Unlike Version 1.0's indiscriminate avoidance based solely on physical point clouds, this new capability significantly elevates the overall intelligence level of the robot.

- Dynamic Parameter Configuration Capability: Version 1.0 Only supports wired configuration via LxCameraViewer on host computer. All obstacle avoidance parameters (such as detection zone size, trigger thresholds, and signal sensitivity) can only be modified when connected to the host computer. Real-time dynamic adjustments are not possible, resulting in low efficiency for scenario adaptation. On the other hand, Version 2.0 introduces a dynamic configuration feature that allows real-time online modification of various parameters without the need for a wired host computer. Users can dynamically adjust detection thresholds, zone ranges, and response logic based on the on-site operating environment, running speed, and specific scenario requirements. This enables rapid switching across multiple scenarios and significantly optimizes both configuration convenience and on-site adaptability.


### Core Function Comparison table

| Feature | Obstacle Avoidance Algorithm V1.0 | Obstacle Avoidance Algorithm V2.0 |
| :--- | :--- | :--- |
| **On-camera Computing** | Supported | Supported |
| **Point Cloud to Robot Coordinate Transformation** | Supported | Supported |
| **Rectangular/Fan-shaped Zone Detection** | Supported | Supported |
| **3-Level Obstacle Avoidance Signal Output (0/1/2)** | Supported | Supported |
| **Non-semantic Object Clustering + Bounding Box Output** | Not Supported | Supported |
| **Ground Void Detection (DEMO Level)** | Not Supported | Supported |
| **Customized Semantic Obstacle Recognition** | Not Supported | Supported (Requires Custom Model) |
| **Parameter Configuration Mode** | Wired Configuration only | Online Dynamic Configuration is also supported |


### Summary

- Version 1.0: Suitable for standardized operation scenarios with flat roads, single types of obstacles, fixed working environments, and where only basic obstacle avoidance functions are required. It meets basic safety needs with lower costs and simple deployment.

- Version 2.0: Designed for advanced operation scenarios featuring complex terrains, diverse obstacle types, and frequent scene switching. It is ideal for applications requiring precise recognition, anti-false-trigger capabilities, ground void danger prevention, and intelligent obstacle avoidance. Its safety, stability, and flexibility are comprehensively superior to Version 1.0.


 
---

##  3. Connection settings

- Before connecting the camera, please complete the following setup: The factory default IP address of the camera is 192.168.100.82. Ensure that your local network port (or Ethernet adapter) is configured to be in the same subnet before establishing a connection. 

- Disable the firewall.

- For more details about IP and Firewall configuration, please see the LxCameraViewer use manual at https://github.com/Lanxin-MRDVS/CameraSDK/wiki/LxCameraViewer-User-Manual 


## Initial setup 

After completing the IP and Gateway configurations above, launch the LxCameraViewer again, and the software will automatically detect cameras on the current network segment. Click to open a camera, and the depth image and point cloud will be displayed automatically, as shown in Figure 3.

<p align="center">
<img alt="PixPin_2026-05-27_10-36-21" src="https://github.com/user-attachments/assets/b2614ba2-faea-40a6-9a3f-2eefa2faf8b1" />
<br>
  <em>Figure 3: LxCameraViewer Display</em>
</p>


Click the [Basic] button on the top toolbar as shown in Figure 4. The basic camera settings will then appear in the status panel on the right, as shown in Figure 4. Scroll down and expand the 3D Settings and Filtering menus to adjust the camera parameters. For S10 Series: You only need to set the Glare Level in 3D Settings to 1; the minimum amplitude value does not need to be configured. When testing high-reflectivity objects, you can also turn the Glare level to 2 or 3 based on your needs. For non-standard vehicle installations and parameter configurations, please contact MRDVS technical support.

<p align="center">
<img alt="Näyttökuva 2026-05-29 kello 12 13 56" src="https://github.com/user-attachments/assets/55a6def7-247f-4826-a4c5-7ab4dd2f7cc1" />
<br>
  <em>Figure 4: Initial setup</em>
</p>


---

## 4. Algorithm Configuration

Depending on your camera model, choose the right algorithm:
| Camera Model | Algorithm Version |
| :--- | :--- | 
| **S10** | Obstacle Avoidance 1.0 | 
| **S10 Pro** | Obstacle Avoidance 2.0 | 

### Step 1: Select Algorithm
After completing the camera parameter configuration, click the [Algorithm] button. The algorithm settings will appear in the status panel on the right, as shown
in Figure 6. Select [Avoid Obstacle] for S10 cameras, and [Avoid Obstacle 2.0]
for all other models. Please note that the version number is displayed only for
[Avoid Obstacle 2.0]; it is not visible for [Avoid Obstacle 1.0].

<p align="center">
<img alt="PixPin_2026-05-27_15-07-35" src="https://github.com/user-attachments/assets/81a1d493-3f9c-4139-837b-dc77cf5fa6ba" />
<br>
  <em>Figure 6: Select right algorithm </em>
</p>

### Step 2: Set Working Mode
Set Working mode to [WORK FOREVER] or [KEEP HEARTBEAT] based on
your need as shown in Figure 7.
The [KEEP FOREVER] mode will establish a long-lasting SDK, TCP/UDP
channel between LxCameraViewer and camera system, after the LxCameraViewer sends a startup command once to the camera system, the avoidance
algorithm in the camera system will continue to run independently and outputting data.
The [KEEP HEARTBEAT] mode add a security confirmation mechanism. The
LxCameraViewer not only has to send the start command, but also has to send a light-weight data package to the camera system every fixed time interval. After
the camera receives the heart leap package, it will reply to the LxCameraViewer
and tell it that the camera system is still alive, and continue to operate and output data. If the camera system hasn’t receive any heartbeat package from the
LxCameraViewer in a fixed time interval, it will assume the connection is lost,
and stop outputing data. Suppose the robot’s main control computer suddenly
crashes, the program fails, or the network cable is accidentally unplugged, preventing LxCameraViewer from sending heartbeat packets. Once the camera
stops receiving these heartbeats, it will assume that the ’brain’ has gone offline
and proactively stop outputting obstacle avoidance data, thereby bringing the
robot to a halt and preventing serious accidents.

Note: The S10 camera does not support the fan-shaped obstacle avoidance zone
type. Using it may cause deviations in the obstacle avoidance results

<p align="center">
<img alt="PixPin_2026-05-27_10-16-12" src="https://github.com/user-attachments/assets/579c3d3d-69c1-4909-87a9-c8bdb7991c99" />
<br>
  <em>Figure 7: Select working mode </em>
</p>

---

##  5. Extrinsic Calibration

Proper calibration ensures the point cloud aligns with the real world.

### Key Parameters

| Parameter | Value | Description |
| :--- | :---: | :--- |
| **Camera angle Roll** | 180 | Camera extrinsics: Roll angle. For a standard upright camera installation, the default value is 180. |
| **Camera angle Pitch** | 90 | Camera extrinsics: Pitch angle. For a standard upright camera installation, the default value is 90. |
| **Camera angle Yaw** | 90 | Camera extrinsics: Yaw angle. The default value is 90. |
| **Camera Position (x)** | 430 | The forward/backward distance between the camera and the AMR, measured in millimeters. The default value is 430. |
| **Camera Position (y)** | 0 | The left/right lateral offset of the camera relative to the AMR's centerline. Set this value to 0 if the camera is mounted exactly in the center. Measured in millimeters. |
| **Camera Position (z)** | 120 | The vertical distance from the camera lens to the ground. Measured in millimeters. The default value is 120. |

### Calibration Steps

### Step 1: View Control
Use the mouse to manipulate the 3D view:
- **Left Click + Drag:** Rotate the view.
- **Middle Click + Drag:** Move the focal point.
- **Right Click + Drag / Wheel:** Zoom in/out.

<p align="center">
<img width="50%" height="50%" alt="PixPin_2026-05-27_10-23-14" src="https://github.com/user-attachments/assets/21cc2c04-9798-4e02-9f52-23a28b2009a7" />
<br>
  <em>Figure 8: Rectangular obstacle avoidance zone </em>
</p>

### Step 2: Choose working mode
When the camera is mounted on the front surface of the AGV, disable all other
image displays and use only the point cloud to modify the camera parameters.
Modify the camera orientation by changing the [Camera position (z)], [Camera
angle Roll], [Camera angle Pitch] and [Camera angle Yaw], so that the gound
generated by point cloud image keeps as parallel as possible with the Coordinates
ground, for example shown as Figure 9.

<p align="center">
<img alt="PixPin_2026-05-28_16-59-10" src="https://github.com/user-attachments/assets/72980539-8f89-4a06-b9ed-e4abd3c9e8b1" />
<br>
  <em>Figure 9: Camera parameter configuration </em>
</p>

### Step 3: Calibration
Click the [Calib param] so that the program automatically fine-tune the camera
parameters and ensures the possible error is corrected as shown in blue box in
figure 10 and 11. Once the point cloud image and obstacle avoidance zone over-
laps correctly, click ”Send Parameters” to synchronize the extrinsic calibration
parameters with other configurations.

<p align="center">
<img alt="PixPin_2026-05-28_17-00-24" src="https://github.com/user-attachments/assets/c7147b4f-8560-4278-9082-6853d5184910" />
<br>
  <em>Figure 10: After automatic fine-tuning </em>
</p>

<p align="center">
<img alt="Näyttökuva 2026-05-28 kello 17 19 29" src="https://github.com/user-attachments/assets/24053b59-5666-4748-9fa3-02d0b86632fa" />
<br>
  <em>Figure 11: After automatic fine-tuning </em>
</p>

---

## 6. Obstacle Avoidance Zone Configuration

### Parameter Definitions

<p align="center">
<img alt="PixPin_2026-06-04_11-15-40" src="https://github.com/user-attachments/assets/0e749d64-f04d-437f-8daf-699200250ab3" />
<br>
  <em> Zone parameters </em>
</p>

| Parameter Name | Value | Parameter Definition |
| :--- | :---: | :--- |
| **Warning Distance (X-Far)** | 2000 | Obstacle avoidance range; distance from the vehicle center in the x-direction. Obstacles beyond this distance are considered safe; the area between Warning Distance x(Far) and Alarm Distance x(Medium) is treated as a warning zone for deceleration, displayed as a yellow area on the interface. Unit: mm. |
| **Alarm Distance (X-Medium)** | 1500 | Obstacle avoidance range; distance from the vehicle center in the x-direction. Obstacles closer than this distance trigger an alarm and stop, displayed as a red area on the interface; the area between Alarm Distance x(Medium) and Warning Distance x(Near) is treated as an alarm zone for obstacle avoidance, displayed as a red area. Unit: mm. |
| **Occlusion Distance (X-Near)** | 600 | Occlusion range; the area closer than Occlusion Distance x(Near) in the x-direction is a blind spot where obstacle avoidance is not possible. Unit: mm. |
| **Avoidance Range Left (Y-Left)** | -810 | Obstacle avoidance range; distance to the left of the vehicle center in the y-direction. Unit: mm. |
| **Avoidance Range Right (Y-Right)** | 1270 | Obstacle avoidance range; distance to the right of the vehicle center in the y-direction. Unit: mm. |
| **Avoidance Range Bottom (Z-Bottom)** | 10 | Obstacle avoidance range; height from the ground. Points below this height are ignored. If set too low, it may cause false alarms due to ranging errors; if set too high, it may filter out larger ground obstacles leading to missed detections. Unit: mm. |
| **Avoidance Height Top (Z-Top)** | 1500 | Obstacle avoidance range; height from the ground. Points above this height are ignored. Unit: mm. |



### Zone Configuration
Choose the [Algorithm index] index to apply different obstacle avoidance
zones. [Algorithm index] are shown in Figure 12 in the blue box. The
[Algorithm index] menu contains of index 0 to 19. Each index refers to
a obstacle avoidance zone configuration set as shown in Figure 10 in the green
box. Number 0 - 6 are seven ready-made obstacle avoidance zone configuration
sets that you can choose, number 6 - 19 are the same configurations. You can
modify each set yourself based on your need, click [Set Parameters] to save the modifications. (Note: If you use TCP, UDP, API as the connection method, you can change index from 0-19, but if you use
IO as the connection, you can only change index 0, 1, 2, 3.

<p align="center">
<img alt="PixPin_2026-05-27_18-40-41" src="https://github.com/user-attachments/assets/aa89a431-f283-4eff-81e2-e6a9eca6cddf" />
<br>
  <em>Figure 12: Obstacle avoidance zone configuration </em>
</p>

- Warning Distance: Represents the camera’s (deceleration) obstacle
avoidance warning range of 2300. This equates to a distance of 1870
mm from the camera (calculated as 2300 minus the camera position of
430), as shown in Figure 15.
- Alarm Distance : Represents the camera’s (stop) obstacle avoidance
alarm range of 1200. This equates to a distance of 770 mm from the
camera (calculated as 1200 minus the camera position of 430), as shown
in Figure 15.
- Masking Distance: Represents the camera’s masking range. This equatesto 20 mm from the camera position (calculated as 450 minus the camera
position of 430), as shown in Figure 15.
- Obstacle Avoidance Range Left (Y-Left): Indicates the obstacle
detection range extending 500 mm to the left of the camera, as shown in
Figure 13.
- Obstacle Avoidance Range Right (Y-Right): Indicates the obstacle
detection range extending 500 mm to the right of the camera, as shown
in Figure 13.
- Obstacle Avoidance Height (Z-Lower): Indicates the detection of
obstacles within 10 mm below the installation height (ground level), as
shown in Figure 14.
- Obstacle Avoidance Height (Z-Upper): Indicates the camera’s de-
tection of obstacles within 500 mm above the ground, as shown in Figure 14.

<p align="center">
<img width="50%" height="50%" alt="Näyttökuva 2026-05-28 kello 17 26 23" src="https://github.com/user-attachments/assets/d89a898f-fa76-4247-abbb-24d74f684323" />
<br>
  <em>Figure 13:  y left, y right </em>
</p>

<p align="center">
<img width="50%" height="50%" alt="Näyttökuva 2026-05-28 kello 17 26 37" src="https://github.com/user-attachments/assets/54e27530-6892-4055-af3d-064b16fc8765" />
<br>  
  <em>Figure 14: on z, below z </em>
</p>

<p align="center">
<img width="50%" height="50%" alt="Näyttökuva 2026-05-28 kello 17 26 12" src="https://github.com/user-attachments/assets/2adf7493-c94d-4c3e-863a-102fa1efa1a4" />
<br>
  <em>Figure 15: Distance </em>
</p>


---

## 7. Networking

Here, we used NetAssist as the communication configuration tool. You can download it from https://www.cmsoft.cn/resource/102.html, as shown in Figure 16. 

You can also use NetAssistant from https://github.com/luokyme/NetAssistant, which includes English documentation, but it has not been tested with this instruction.


<p align="center">
<img width="50%" height="50%" alt="Näyttökuva 2026-06-02 kello 9 42 36" src="https://github.com/user-attachments/assets/c65c8633-d35c-4e83-b12c-712988e689ae" />
<br>
  <em>Figure 16: Download site </em>
</p>


### API Communication

The API  Communication supports various environments including Windows, Linux, and ARM, as well as programming languages such as C++, C#, Java, ROS1, and ROS2. 

For Windows, once the host computer software is installed, the files of Software Development Kit and example source code can be found in the installation directory (e.g., D:\Program Files\Lanxin-MRDVS). For Linux environments, please contact MRDVS technical support or download the SDK from the official website.

Directory Overview:
- Document: Contains the user manuals for the SDK and host computer software.
- FirmWare: Directory for storing camera firmware packages.
- Sample: Contains the source code for sample projects. Select the appropriate example based on your development environment.
- SDK: Directory containing the SDK library files. You can configure the environment variables according to your development needs.
- For obstacle avoidance applications, please refer to the obstacle avoidance API source code located at: Sample/C/application_obstacled.




### UDP Communication

Definition of the UDP Hex Data Packets Sent by the Obstacle Avoidance System:



| No. | Transmission Direction | Message | Obstacle Avoidance Result |
| :--- | :--- | :--- | :--- |
| 1 | Camera -> Device | `ACED0410XX000000` | No Obstacle, XX represents current obstacle avoidance parameter |
| 2 | | `ACED0410XX000001` | Warning Deceleration |
| 3 | | `ACED0410XX000002` | Alarm Stop |
| 4 | Device -> Camera | `ACED040000000000` | Establish UDP Connection |
| 5 | | `ACED041A00000000` | Obstacle Avoidance Parameter 0 |
| 6 | | `ACED041A00000001` | Obstacle Avoidance Parameter 1 |
| 7 | | `ACED041A00000002` | Obstacle Avoidance Parameter 2 |
| 8 | | `ACED041A00000003` | Obstacle Avoidance Parameter 3 |
| 9 | | ... | (and so on up to Parameter 19) |
| 10 | Device -> Camera | `ACED041B00000000` | Set Current Parameter as Default Parameter |
| 11 | Camera -> Device | `ACED041B00000001` | Default Parameter Set Successfully |


- Step 1: When connecting via UDP, use the communication configuration tool to test the communication with the camera, and select hexadecimal format for both sending and receiving data. Open the LxCameraViewer, make sure the Local Host port in the communication configuration tool is set to 6688(Communication port that camera system use as default). Then click Open. 

<p align="center">
<img alt="PixPin_2026-06-01_05-29-59" src="https://github.com/user-attachments/assets/f6168daf-4f59-4f8a-b3c8-5e22c17a3f79" />
<em>Figure 17: Local Host port in communication configuration tool</em>
</p>


- Step 2: Enter the camera's IP address (as shown in LxCameraViewer) followed by the port number 6688 into the Remote section of the communication configuration tool (refer to the red box in Figure 18). Next, input the initial hex data package (as shown in the blue box). For the initial communication, send the No. 4 command to establish a UDP connection. Once the connection is established, obstacle avoidance results will be transmitted automatically at a frequency matching the current image frame rate. After modifying any parameters, you can verify the changes by checking the message sent from the camera to the device—note that the XX in the No. 1 message represents the current parameter.

<p align="center">
<img alt="PixPin_2026-06-01_05-29-20" src="https://github.com/user-attachments/assets/3a0411e4-8556-4deb-9108-f3a9102c79ab" />
<em>Figure 18: Send initial communication package</em>
</p>



- Step 3: The parameters set via communication configuration tool remain effective until the camera is restarted, unless the power is cut off or they are modified using other communication methods. If you want the settings to persist after a power cycle, you can use the No. 10 message to save them as default parameters. Saving as default parameters is a feature unique to TCP&UDP communicatio.

- If the camera IP has been changed, use: Camera IP:6688; taking changing from parameter 19 to parameter 0 as an example, click to send the No. 5 data. The sign of a successful setting is that the 5th byte changes from 0x13 (parameter 19) to 0x00 (parameter 0), as shown in the figure below.


### TCP Communication

Definition of the TCP Hex Data Packets Sent by the Obstacle Avoidance System:


| ID | Transmission Direction | Message | Obstacle Avoidance Result |
| :--- | :--- | :--- | :--- |
| 1 | Camera -> Body | `ACED0410XX000000` | No Obstacle, XX represents the current obstacle avoidance parameter |
| 2 | | `ACED0410XX000001` | Warning Deceleration |
| 3 | | `ACED0410XX000002` | Alarm Stop |
| 4 | Body -> Camera | `ACED041A00000000` | Obstacle Avoidance Parameter 0 |
| 5 | | `ACED041A00000001` | Obstacle Avoidance Parameter 1 |
| 6 | | `ACED041A00000002` | Obstacle Avoidance Parameter 2 |
| 7 | | `ACED041A00000003` | Obstacle Avoidance Parameter 3 |
| 8 | | ... | (and so on up to Parameter 19) |
| 9 | Body -> Camera | `ACED041B00000000` | Set Current Parameter as Default |
| 10 | Camera -> Body | `ACED041B00000001` | Default Parameter Set Successfully |

- Step 1: Before using TCP communication, you need to confirm whether the currently used obstacle avoidance area has been set on the LxCameraViewer.

- Step 2: Open the communication configuration tool, fill in the camera IP address shown in LxCameraViewer into the remote host section, and default port number 6688 into the Remote host section. As shown in Figure 19. 


- Step 3: Select hexadecimal format for both sending and receiving data, and then click Connect to start the communication. After establishing the TCP connection, obstacle avoidance results will be sent automatically, and the sending frequency is related to the current image frame rate. After modifying parameters, you can confirm whether the modification is successful through the message sent from the camera to the body; the 'XX' in the No. 1 message represents the current parameter.

<p align="center">
<img alt="PixPin_2026-06-01_07-49-47" src="https://github.com/user-attachments/assets/1539ddfc-730d-47a0-bee8-12bbee6750b7" />
<em>Figure 19: TCP Connection</em>
</p>

- Parameters set via TCP remain effective until the camera is restarted, unless the power is cut off or other communication methods are used to modify them. If you want the parameters to remain effective after a power cycle, you can use the No. 10 message to save them as default parameters. The function of saving as default parameters is unique to TCP&UDP communication.


---

## 8. Outputs
You can see the real-time outputs at Algorithm -> Algorithm output, shown in Figure 20. 

<p align="center">
<img alt="PixPin_2026-05-29_16-26-25" src="https://github.com/user-attachments/assets/010ed1e6-5ee4-4180-9725-4e50572b9c0b" />
<br>
  <em>Figure 20: Output </em>
</p>



- 0 Indicates normal operation with no obstacles detected.
- 1 Indicates an obstacle detected within the warning zone.
- 2 Indicates an obstacle detected within the alarm zone.

---
## 9. Backup and synchronizing

After configuring the parameters through the steps above, you can back up the
avoidance.json file located in the software installation path \Tools\params\Current Camera ID\avoidance.json to quickly synchronize the obstacle avoidance parameters across different cameras. To do this, simply start the camera, execute the ”Load Configuration from File” command, select the backed up avoidance.json file, and wait for the settings to be applied.

---
## 10. Troubleshooting

### Low Ground Objects
Objects directly on the ground cannot be avoided. In obstacle avoidance applications, we generally use the ground as the reference for extrinsic parameter configuration. If low obstacles on the ground fail to trigger obstacle avoidance, please refer to the following solutions:

- No bounding box around the obstacle in the point cloud: Verify
whether the “Obstacle Avoidance Height (Z-Lower)” value is positive. If it is, temporarily set it to 0 to check if the obstacle can be detected and boxed. If it still fails, consider adjusting the camera’s installation height.

- Bounding box appears but output remains 0: This issue may be caused by an incorrect camera installation height configuration. It is recommended to adjust the camera’s installation height.

### Obstacle Avoidance Parameters Not Taking Effect

This issue typically occurs due to the following reasons:
- The “Apply Settings” button was not clicked after configuring the parameters.
- Invalid parameters were modified, causing the settings to fail.
- An unstable camera connection or disconnection resulted in a failure to deliver the parameters.

###  Installation Structure Interference

Camera data anomalies may occur under the following structural conditions:
- Surrounding structures during installation obstruct the camera’s field of view (FOV).
- Poor structural design places the camera too far back, causing FOV interference.
- The protective film on the camera lens has not been removed.
- Additional protective glass has been installed over the camera lens.
