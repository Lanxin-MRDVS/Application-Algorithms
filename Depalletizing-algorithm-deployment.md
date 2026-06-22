# Vision Guided Depalletizing: AW3 Platform & PalletEye Deployment Guide

## 1. Instruction

AwareSight3 (also known as AW3) is an application management platform designed for industrial vision algorithms. It is responsible for device connection, authentication, camera parameter configuration, and the management and deployment of algorithm parameters. PalletEye (also called PE) is a built-in algorithm module within the platform, specifically tailored for soft bag and carton unstacking. Leveraging RGB-D camera data, it delivers capabilities such as pallet cargo recognition, region calibration, hand-eye calibration, grasp pose estimation, and dimension detection. It is widely applied in industrial pallet unstacking scenarios. This manual serves to guide operators through the entire process of software deployment, device connection, applying for an algorithm license, parameter configuration, unstacking function debugging, and template management.

### 1.1 Interface overview

The overall interface of the AW3 platform is primarily divided into four major functional sections: 1.Connection Management Section; 2.Parameter Configuration Section; 3.Display Configuration Section ; and 4.Visualization Section. These sections operate independently yet work in synergy, covering the full operational workflow of device access, parameter configuration, visual observation, and algorithm execution (as shown in Figure 1).

![PixPin\_2026-06-01\_10-40-42](https://github.com/user-attachments/assets/ad3c08cf-d85c-40c1-b935-9b1b1934ab76)\
_&#x46;igure 1：Interface overview_

## 2. Display Configuration Section

Interface & Language Settings: Used to configure the real-time display type and system language of the software interface. Parameters take effect immediately without requiring additional saving or distribution, adapting to various configuration and observation scenarios.

![PixPin\_2026-06-04\_08-11-06](https://github.com/user-attachments/assets/48ecdaf1-d922-4c29-9b9e-5997a6b6cf7c)\
_&#x46;igure 2: Display Configuration_

## 3. Visualization Section

![PixPin\_2026-06-04\_08-13-07](https://github.com/user-attachments/assets/7541fda0-d06a-4bf3-b985-470161af6616)\
_&#x46;igure 3: Visualization_

## 4. Parameter Configuration Section

The Parameter Configuration Section contains five tabs, the Device Connection, the Algorithm enable, the Parameters, the Soft-pack depalletizing, and the Result log.

### 4.1 Device Connection tab

When clicking the Device Connection menu, the content will then be at the right side of the displays, as shown in Figure 4 red box. The Center Connection section shows the information of the center AlgPlatformViewer is connected to.

* Center Address: The IP address of the center that AlgPlatformViewer is connected to.
* Center Port: The port number used by the center to transport all operational data streams. This includes sharing information about cameras connected to this center with other centers, as well as importing real-time 3D image data from cameras.
* Broadcast Address: Defaults to "auto". In this mode, the center automatically broadcasts its IP address and Discovery Port information via a UDP packet.
* Discovery Port: The port number used by the center to broadcast its IP address and port details to other centers within the same subnet. When a center receives a discovery packet from another center, it sends a response. This mechanism allows centers to discover each other and establish collaboration.
* Timeout Value: The timeout duration in milliseconds (ms). This defines how long AlgPlatformViewer will attempt to connect to the center before stopping if a connection cannot be established.
* Discover Centers: Clicking this button detects all centers on the same subnet and displays them below, and AlgPlatformViewer will automatically connect to the first center in order. By clicking a center in the list, all virtual cameras created by that center will then appear in the Connection Management section. You can switch to a specific virtual camera's view in the Display section by clicking the virtual camera number.

(Virtual cameras are designed to support multi-camera cooperation in the future. Currently, each virtual camera is only mapped to a single physical camera.)

![PixPin\_2026-06-02\_08-32-02](https://github.com/user-attachments/assets/36f48856-18df-491d-9da3-2466a98f3fc8)\
_&#x46;igure 4：Connect to center_

* Connect center: By clicking this button, the AlgPlatformViewer will manually connect to a selected center. This is for the case if the subnet routing doesn't support UDP broadcast discovery.

### 4.2 Depalletizing

The Depalletizing Configuration Interface is a core feature of the PalletEye algorithm. It integrates task template/mode settings, algorithm parameter configuration, and core operational capabilities. Designed to support parameter configuration, calibration, task template management, and algorithm computation for soft-pack and carton depalletizing scenarios, it is fully adapted to the demands of routine industrial operations and on-site tuning.

![PixPin\_2026-06-03\_08-14-13](https://github.com/user-attachments/assets/8a8d5f4b-1c5b-426d-b8ee-d078f8e8ffd1)\
_&#x46;igure 5：Depalletizing Configuration_

#### 4.2.1 Choose Template and Mode

1. Fetch Current Parameters: By clicking this button, the AlgPlatformViewer fetches all the Global-, Region-, and Calibration parameters saved on the center connected. The fetched parameters are then loaded into the Global-, Calibration-, Region settings for visualization and further configuration if needed.
2. Template Selection: Select saved Global settings template via a dropdown menu for quick switching between scenario-specific configurations, such as for different shapes of bags. For soft-bags, we recommend to use template 6.
3. Material Type Switching: Supports switching between two material types—Soft-pack (bag) and Carton (Box)—to adapt to different depalletizing target recognition logics.
4. Apply Calibration to All Templates and Distribute: This button applies the Region and Calibration settings to all other templates. The logic is that Global settings contain parameters specific to a depalletizing target, which may change when cargo types change. However, the detection area and camera calibration remain constant since the robot's physical position does not change. Therefore, when the cargo type changes, you only need to update the Global settings, without having to re-enter the Region and Calibration parameters every time.
5. Operation Mode Switching: Simple Mode: Parameters are fixed. It performs only basic validation on cargo dimensions without advanced algorithm features, making it suitable for standardized, routine depalletizing scenarios. Expert Mode: Unlocks full custom parameter configuration and enables advanced features like parcel merging. This mode is designed for complex working conditions and scenarios requiring refined recognition (UI to be continuously optimized).

![PixPin\_2026-06-03\_08-18-31](https://github.com/user-attachments/assets/9ac618ee-a4be-4569-babb-f97960a7bbfc)\
_&#x46;igure 6：Choose template and mode_

#### 4.2.2 Global Settings

The Global Settings defines the core filtering and recognition parameters for depalletizing target detection. It is used to control cargo detection accuracy and filtering rules. The parameters are described as follows:

1. Fill Ratio: Determines the threshold of how well the detected target fills the detection frame. Recommended value is 0.7. Cargo with a fill ratio lower than this threshold will be filtered out to avoid invalid or interfering targets.
2. Standard Dimensions (L x W mm): Sets the standard length and width benchmarks for the target material.
3. Length/Width Range (mm): Defines the valid length and width intervals for cargo. Targets falling outside these ranges are automatically filtered.
4. Layer Height (mm): This parameter is used to filter cargo by layer height and distinguish items across different stacking levels. For example, if the Layer Height is set to 200 mm, it means that when soft-bags are stacked, the height of a single bag (e.g., 200 mm) determines the height of each layer. Since the robot picks only one bag from the top of the stack at a time, bags in the second layer and all layers below will be filtered out from further computation.
5. Arrangement Order: Defines the priority order for the algorithm to recognize cargo. It defaults to "Near to far," meaning the system prioritizes recognizing the nearest cargo first. This setting is crucial in industrial environments where cargo may not be stacked neatly, and items on the same layer might partially overlap. This function prevents the system from attempting to pick up a top layer cargo that has another item partly on top of it, which could cause displacement or instability during retrieval. For example in Figure 7, you can see the arrangement order as the green number.
6. Advanced Toggles \[Under Development]: Includes options for enabling large-size splitting, parallel alignment correction, multiple results at once, and occlusion detection. In the current version, these are reserved configuration items and are not yet active.

![PixPin\_2026-06-03\_08-19-04](https://github.com/user-attachments/assets/39a12f80-453a-4253-81d5-8497591b3fed)\
_&#x46;igure 7：Global Settings_

If the cargo's volume and size exceed the maximum Length/Width range in the Global settings, or if the target cargo is too small and falls below the minimum Length/Width range, the system will filter out the cargo and will not detect it as a target. This is shown in Figure 8. If that happened, switch template or change Global settings parameters, and then click Save and Send, and then Single trigger.

![PixPin\_2026-06-03\_09-32-28](https://github.com/user-attachments/assets/1ef658d4-b981-4902-857e-a5799eaf16c5)\
_&#x46;igure 8：Error example_

#### 4.2.3 Area Settings

Used to customize the spatial detection region of the algorithm. By setting the maximum and minimum values for the X, Y and Z, it limits the camera's effective recognition space and filters out interfering targets outside the field of detection range.

![PixPin\_2026-06-03\_08-20-34](https://github.com/user-attachments/assets/422ed648-a506-43c8-a68f-87bbdc06a61e)\
_&#x46;igure 9：Area Settings_

For example, if the Area is set too small and part of the target cargo falls outside it, the excluded area will not be counted towards the cargo's size. If the remaining part inside the region does not meet the minimum Length/Width requirements in the Global Settings, the cargo will not be detected as a target. This is shown in Figure 10. If that happened, configure the Area Settings and change the area size, then click Save and Send and Single Trigger.

![PixPin\_2026-06-03\_10-27-36](https://github.com/user-attachments/assets/35a488b1-513e-4d8f-a0d8-a6a4af056177)\
_&#x46;igure 10：Error example_

#### 4.2.4 Output Settings \[Under Development]

All configuration options in this section are currently under development, and settings are not yet active; the interface is reserved for future use, including Euler angle type, RZ range, Reverse range, Output type (3D/2D), rxry tilt range, Output unit (deg/mm), Output precision.

![PixPin\_2026-06-03\_08-19-45](https://github.com/user-attachments/assets/3dd318a9-3277-48a6-87f8-c64dfab89143)\
_&#x46;igure 11：Output Settings_

#### 4.2.5 Calibration Settings

Used for managing hand-eye calibration parameters between the camera and the robotic arm. Configurable parameters include Euler angles, translation vector, offsets, and the tool coordinate system RT, which serve as the calibration benchmark for depalletizing pose calculations. Used for initial calibration.

* Euler Angles: Represents the orientation (rotation) of the robotic arm in 3D space. It describes how the robotic arm is tilted or turned using three specific angles: Roll, Pitch, and Yaw.
* Translation Vector: Represents the position of the robotic arm in 3D space. It defines the robotic arm's exact location relative to a reference point (origin) using X, Y, and Z coordinates. It tells the system how far the tool tip is from the robot camera in the length, width, and height directions.
* Offset: Represents an intentional adjustment or shift applied to a target position. It adds a specific distance to the original coordinates to fine-tune the final location (e.g., to avoid collisions or adjust a gripping point).
* Tool frame R: It displays the X, Y, and Z distances from the robot's end flange to the robot's gripper tool.
* Tool frame T：It specifies the rotational angles (expressed in Euler angles: Rx, Ry, Rz) of the tool relative to the robot's end flange.

![PixPin\_2026-06-03\_08-20-11](https://github.com/user-attachments/assets/bc8e03b4-efba-4134-8a72-c49b4a901501)\
_&#x46;igure 12：Calibration Settings_

#### 4.2.6 Hand-eye calibration

* Add point: Enter the X, Y, and Z value of the teaching point into the input box and click the [Add Point] button to add the point's coordinates to the corresponding coordinate area.
* Import from clipboard: After pasting coordinate data from other devices into the input box, click this button. The system will automatically recognize the format and enter the coordinate data.
* Camera coordinate area: Displays the coordinates of the four camera teaching points.
* Robot coordinate area: Displays the coordinates of the four robot teaching points.
* Delete point/Delete all: Delete a single point or all coordinates in the coordinate area.
* Auto add/Detect markers: When you select the [Auto Add] mode, the hand-eye calibration tool enters auto-add mode. Place a calibration board at the pallet position so that it is fully visible within the camera's field of view. Then, click the [Detect Markers] button. The tool will automatically detect the coordinates of the four corners of the calibration board, eliminating the need to enter them manually.
* Left handed coordinate system: Check this option to switch the coordinate area to a left-handed coordinate system.
* Calibration: Click the [Calibration] button to start the hand-eye calibration.

[Gripper tool offset] section
* Euler angles: Enter the Euler angles for the robot gripper tool (e.g., the robot wrist).
* Offset: Enter the offset values for the robot gripper tool.
* Camera teaching point coordinates/Robot teaching point coordinates: These sections are primarily used to verify calibration results. By entering a point coordinate from the camera coordinate area, the system will automatically transform it into the corresponding robot coordinate, which will then be displayed in the Robot Teaching Point Coordinates section.


![PixPin\_2026-06-03\_08-21-01](https://github.com/user-attachments/assets/4ce00fda-f751-4fae-a83d-4dce1f7a3740)\
_&#x46;igure 13: Hand-eye calibration_

**Why is hand-eye calibration necessary?** 

In practical applications, robots need to combine visual information to execute tasks. The robotic arm operates within its own coordinate system and knows its exact position and orientation (e.g., XYZ values and angles) within it. Similarly, the camera operates within its own coordinate system, with the optical center serving as the origin, and it knows the position and orientation of the target object relative to its lens. However, the camera system does not know its spatial pose relative to the robot's base. This means it can only determine coordinates within its own system and cannot directly map them to the robot's coordinate system.

Hand-eye calibration is designed to establish the coordinate transformation matrix between the "eye" and the "hand". Only after this step is completed can the robot accurately translate the 3D point cloud coordinates captured by the camera into control coordinates that the robotic arm can understand and execute, thereby achieving true "eye-to-hand" coordination.

#### 4.2.7 Buttons

1. Single trigger: Click the button to execute a single image capture and depalletizing calculation. It updates detection results (such as cargo grasping pose and dimensions) in real-time, suitable for single-run debugging and verification.
2. Add Template/Delete template:

* Add template： Click the button and enter a custom name to create and save a new template.
* Delete Current Template: One-click deletion of the currently selected template to clear invalid scene configurations.

3. Region calibration: Click the button to execute the region calibration. The algorithm identifies all cargo targets within the RGB field of view, selects the most centered cargo as the base detection area, expands outward by a fixed range, and generates the valid detection area with a visual display of the calibration result.
4. Hand-eye calibration: During the initial setup, clicking this button will launch the hand-eye calibration tool. The purpose of this tool is to align the separate coordinate systems of the camera and the robot arm. The "Camera Coordinate" section displays the X, Y, Z value of a specific point within the camera's coordinate system showing the camera's location. Below this, an RGB image shows four reference points on the tray. You need to move the robot arm's tip to each of these points and input the corresponding coordinates into the "Robot Coordinate" section. Once you click OK, the algorithm will unify the camera's and robot arm's coordinate systems, determining the precise spatial relationship between them.
5. Save and send: Saves and deploys all current template parameters (detection, calibration, and area configurations) to the camera device. Parameters are persisted and will not be lost after a device restart.

![PixPin\_2026-06-03\_08-21-01](https://github.com/user-attachments/assets/4d7dcb14-2298-4e11-a79e-3f79b4b49614)\
_&#x46;igure 14: Buttons_

## 5. Communication protocol
Currently, the product's communication protocol system supports TCP connections and custom formats tailored to specific client requirements. Its core module is external triggering protocols. The overall architecture is highly flexible and extensible, supporting various built-in protocols as well as custom extensions. Below is a comprehensive summary of the communication protocol system:

### 5.1 Triggering Protocols

The system supports multiple formats of TCP triggering protocols. After a client sends a request, the server executes the algorithm and returns the result. All protocols support controlling coordinate system transformations (e.g., left-handed vs. right-handed systems) through parameters such as coordinate_system.

HnpsA Raw Frame Protocol:
- Features: Minimalist text commands with no additional termination characters required.
- Format: 3D<CameraID><SoftpackCount> (e.g., 3D15).
- Response: Fixed format 3DA...AOK.

Standard Softpack JSON Protocol (softpack_json)
- Features: Standard JSON interaction; the response contains only the JSON body without any extra protocol headers.
- Request: {"action":"3D","type":5}.
- Response: Supports outputting four values [x,y,z,rz]. Alternatively, it can append length and width to output six values [x,y,z,rz,length,width] via configuration. For multiple targets, the data is expanded sequentially.

Headerless Softpack JSON Protocol (plain_softpack_json)
- Features: Lightweight JSON; requests only require {"action":"3D"}.
- Response: Contains only pos and result; the type field is not returned.

Lingzhi Softpack JSON Protocol (lingzhi_softpack_json)
- Features: Compatible with legacy customer protocols.
- Response: A mandatory protocol header 0x7F 0x7F is prepended before the JSON. The internal field order within the JSON is strictly fixed as pos, followed by result.

### 5.2 Architecture Design and Extension Specifications

The communication framework adopts a highly decoupled design for convenient secondary development:

- Extending Publish Protocols: Inherit the IProtocolPublisher interface, implement the sending logic in the publish method, and register it via the factory class to take effect.

- Extending Trigger Protocols: Inherit the ITriggerProtocol interface to handle listening, request parsing, and calling a unified handler function, eventually encoding and returning the response. This design ensures the protocol layer is completely independent of underlying camera modules, facilitating horizontal replacement.

- Integrating New Algorithms: Supports trigger_only mode, where algorithms execute solely upon receiving external triggers. Algorithms must return a string result, which is distributed by the unified ResultDispatcher. Timeouts return error code -3 by default.

### 5.3 Key Considerations

- Port Separation: The listen_port for receiving triggers and the send_port for actively publishing results are two independent configuration items.

- Timeout Control: timeout_ms governs both the trigger wait time and the TCP publish wait time. In production environments, this should be reasonably configured based on the maximum expected execution time of the algorithm.

- Independent Channels: The UI-side CameraPing uses the gRPC protocol, operating independently from the ResultDispatcher, which exclusively handles result publishing and external triggers.


## 6. Deployment example

This chapter provides a complete deployment configuration process for the AW3 platform combined with the PE flexible packaging depalletizing algorithm. It serves as a reference for standardized on-site configuration and is applicable to scenarios such as initial deployment of new machines, site relocation, and cargo template resets.

#### Step 1: Launch the Software

Open AlgPlatformViewer.exe to run the AW3 host software.

#### Step 2: Verify Network Environment

Ensure that the host computer and the camera algorithm module are on the same local area network (LAN) subnet to guarantee normal communication, discovery, and connection of the devices. For more details about IP and Firewall configuration, please refer to the LxCameraViewer user manual at https://github.com/Lanxin-MRDVS/CameraSDK/wiki/LxCameraViewer-User-Manual

#### Step 3: Deploy Algorithm Firmware [Under development]

Write the PE depalletizing algorithm to the algorithm module via the platform's firmware upgrade feature. (Note: This feature is currently under development; in the current version, algorithm deployment must be completed in advance by the R\&D team.) The algorithm module will automatically restart after the firmware update is complete.

#### Step 4: Connect to the Device

After the device restarts, return to the \[Device Connection] interface. Click the \[Discover centers] button to refresh the LAN connection as shown in green box. Select the center to which your desired camera is connected from the device list as shown in red box, click it, and camera options connected to that center will display on the left of the screen as shown in blue box. Click on the virtual camera option and click the camera you want to establish connection with. Then click \[Connect to Center] button.

![PixPin\_2026-06-04\_05-40-02](https://github.com/user-attachments/assets/2c2e76f1-2433-4b01-bcfb-1413211e26d0)\
_&#x46;igure 15: Connection_

#### Step 5: Activate Algorithm Authorization

Switch to the [Algorithm enable] tab, select the Soft-bag Depalletizing algorithm as shown in blue box, click [Algorithm Authentication] button as shown in red box, and obtain the authorization request key by clicking [Get request key]. Submit this key to the MRDVS FAE personnel to apply for a formal License. Once received, paste the authorization key into the License input box and click [Apply License] to activate the algorithm.

![PixPin\_2026-06-04\_05-43-36](https://github.com/user-attachments/assets/d2762816-727e-4849-9af0-dfb309032f5e)\
_&#x46;igure 16: Activate algorithm_

#### Step 6: Configure Basic Camera Parameters

Switch to the [Parameters] tab, select the right camera parameter template matching the business need and camera model at [camera template], and click [Deploy Camera template] to complete the initialization of the camera's parameters.

![PixPin\_2026-06-04\_05-48-48](https://github.com/user-attachments/assets/08526776-d984-40d4-946c-ea63e5d65862)\
_&#x46;igure 17: Basic camera parameters_

#### Step 7: Configure Depalletizing Parameters

Enter the [Depalletizing] tab, select the corresponding cargo template at [cargo template], for soft-bags, we recommend to use template 6, then select the [material type] to "Bag" and switch the application mode to "Expert Mode." Based on the actual volume and size of the on-site cargo, you can choose the pre-defined [cargo template], which will automatically set the Global settings parameter or sequentially set Global settings parameters such as standard size, length range, width range, and layer height to adapt to the on-site working conditions.


![PixPin\_2026-06-03\_08-18-31](https://github.com/user-attachments/assets/9ac618ee-a4be-4569-babb-f97960a7bbfc)\
_&#x46;igure 18: Depalletizing configuration_


#### Step 8: Hand-Eye Calibration

Execute the hand-eye calibration process to establish the coordinate alignment between the camera and the robotic arm. First, enter the coordinates of the four corners of the pallet into the camera coordinate area. Note that the origin of this area is the optical center of the camera. Next, manually move the robotic arm to each of the four points, tap the point once, and enter the corresponding robotic arm coordinates into the robot coordinate area. Finally, click the [Calibration] button. This will persistently save the calibration parameters to the camera device and automatically apply the [Calibration Settings].

#### Step 9: Area Calibration

The software will automatically identify the cargo within the field of view and generate the valid detection frame, and automatically complete the region calibration. If you want to manually configure the area, remember to click [save and send] button after configuration, to send the new area data to the center.

![PixPin\_2026-06-04\_05-56-00](https://github.com/user-attachments/assets/3dffb6fa-f92a-4253-8d2e-33729aac709e)\
_&#x46;igure 19: Area calibration_

#### Step 10: Test the result

Click Single Trigger to execute a single algorithm detection. Observe the results, including cargo recognition, grasping pose, and dimension output, to determine whether the detection performance is reasonable and meets the on-site depalletizing requirements. You can also see the results at \[Result log] tab.

#### Step 11: Communication Verification

Request results directly from the algorithm module according to the communication protocol, and observe the corresponding changes on the AW3 interface.

#### Step 12: Efficiency Verification

The latency from sending the request to receiving the result must be less than 2500ms.

## 7. Visual Inspection

### 7.1 Algorithm error codes

| Error Code | Description                                                     |
| ---------- | --------------------------------------------------------------- |
| 0          | Success                                                         |
| -1         | Too few point clouds after AOI cropping                         |
| -2         | Inference failed (model returned no results)                    |
| -3         | Too few point clouds after filtering                            |
| -4         | Clustering resulted in empty set                                |
| -5         | No valid soft packages detected                                 |
| -6         | Obstruction detected in the grasping area                       |
| -7         | Upper packages filtered out; grasping lower layer is prohibited |
| -9         | Package exceeds image boundaries                                |
| -10        | Input image is empty or has abnormal dimensions                 |
| -100       | Unknown / Initial error                                         |
| -101       | Pipeline parameters not configured                              |

**Severe Exception Rendering:** \
When critical anomalies are detected, the system triggers two types of visual warning overlay

| Render Content | Error Type |
| :--- | :--- |
| 🔴Red semi-transparent background + Centered "OBSTACLE DETECTED!" | OBSTACLE_DETECTED (-6) |
| 🔴Red semi-transparent background + Centered "BAG OUT OF IMAGE!" | BAG_OUT_OF_IMAGE (-9) |
| `err code=-5, template: xxx` | NO_VALID_BAG (-5) |
| `err code=-7, template: xxx` + "UPPER FILTERED - BLOCK LOWER PICK" | UPPER_FILTERED_BLOCK (-7) |
| `err code=-100, template: xxx` | UNKNOWN (-100) |

![d4e7c26e94fd2aebb9dd145dc012f73b](https://github.com/user-attachments/assets/cbb794c4-d677-4e03-8511-45022ce7d960)\
Figure 20: Algorithm error code



### 7.2 Package error codes
When a package parameter configuration error occurs, the error text is displayed in black on the package.

| Error Code | Description                                       | RGB Render Content |
| ---------- | ------------------------------------------------- | ------------------ |
| 0          | Normal detection                                  | — (Not rendered)   |
| 1          | No valid depth (q.z < 0.1)                        | — (Not rendered)   |
| 2          | No contour after morphological processing         | — (Not rendered)   |
| 3          | Fill rate does not meet the standard              | `FR {fill_rate}`   |
| 4          | Contour too small (w <= 20 or h <= 20)            | — (Not rendered)   |
| 5          | Out of AOI range                                  | — (Not rendered)   |
| 6          | Too few contour points (< 100)                    | — (Not rendered)   |
| 7          | Point cloud is empty outside the AOI              | `NoPC`             |
| 8          | Too few valid plane points after normal filtering | `NoPlane`          |
| 9          | Multiple vertical clusters                        | `MultiClu`         |
| 10         | Width mismatch                                    | `W{width}`         |
| 11         | Length mismatch                                   | `L{length}`        |
| 12         | Both length and width mismatch                    | `SZ {L}x{W}`       |
| 13         | Abnormal z-value for p1/p2 points                 | `PtBad`            |
| 14         | Classified as a lower-layer package               | `below`            |
| 15         | Merged into another package                       | — (Not rendered)   |
| 16         | Center point z-value out of range                 | `BadCtr`           |
| 17         | Suppressed by NMS (Non-Maximum Suppression)       | — (Not rendered)   |
| 18         | Mask is invalid or empty                          | — (Not rendered)   |
| 19         | Abnormal aspect ratio                             | `AR {ratio}`       |
| 99         | Unknown error                                     | `E{code}`          |

<img alt="5cb328cb759200ecaac12ae9db5b9e29" src="https://github.com/user-attachments/assets/c05b3e6f-fcde-47ec-bbdc-570dd23a9242" />\
Figure 21: Package error codes 
### Status Indicators
The top HUD provides real-time telemetry regarding the current palletizing stack status.

| Text Indicator | Meaning |
| :--- | :--- |
| **top bags** | Actual number of top-layer bags / Total count |
| **irregular** | Number of bags with non-compliant dimensions (still unqualified after merging) |
| **invalid_render** | Successfully rendered illegal/invalid bags |
| **invalid_skip** | Skipped illegal/invalid bags |
| **is_ok** | Whether the stacking is within the image boundaries |

<img alt="7c42c22d1705cc40657156525cfc2a44" src="https://github.com/user-attachments/assets/d4ef2369-929c-4c60-8436-38dfb43c9797" />\
Figure 22: Status indicators 

## 8. New features coming

### 8.1 Safety Detection Function

This function detects whether there are any obstructions above the stacked packages. The relevant parameters include:

* Safety detection enable/disable
* Safe height lift distance
* Obstruction size threshold

**Detection Logic:** When safety detection is enabled, a safety platform is established by adding the "Safe height lift distance" to the highest detected package. The system then checks if there are any objects between the camera and this safety platform that exceed the "Obstruction size threshold." If an obstruction is detected, all detected package information will be cleared. The RGB display will appear as follows:

### 8.2 Transition Point

To facilitate robotic arm path planning, the transition point calculation function can be enabled. The adjustable parameters include:

* Output transition point (Enable/Disable)
* Extension distance

### 8.3 Package Sorting Method

Detected packages can be sorted in different ways to adjust the grasping sequence. The specific mapping is as follows:

* `0`: Z min to max
* `1`: X min to max
* `2`: X max to min
* `3`: Y min to max
* `4`: Y max to min

### 8.4 Aspect Ratio Limit

The maximum aspect ratio for packages can be configured. The minimum aspect ratio is fixed at 1.

### 8.5 PCA for Package Pose Calculation

You can configure whether to enable PCA (Principal Component Analysis) for package pose calculation in the template. While PCA can still calculate the pose even if the package point cloud has voids, excessive incompleteness in the point cloud will affect the accuracy of the pose results.

### 8.6 Package Merging

This function addresses the issue where a single soft package with wrinkles is mistakenly recognized as two (or more) separate packages. When enabled, the system will automatically merge them into a single complete package.
