# Depalletizing Deployment Guide

[Documentation Home](../../../README.md) / [Depalletizing](../README.md) / Deployment Guide

For the AW3 (AwareSight3) platform and PalletEye module.

## 1. Instruction

AwareSight3 (also known as AW3) is an application management platform designed for industrial vision algorithms. It is responsible for device connection, authentication, camera parameter configuration, and the management and deployment of algorithm parameters. PalletEye (also called PE) is a built-in algorithm module within the platform, specifically tailored for soft bag and carton unstacking. Leveraging RGB-D camera data, it delivers capabilities such as pallet bag/box recognition, region calibration, hand-eye calibration, grasp pose estimation, and dimension detection. It is widely applied in industrial pallet unstacking scenarios. This manual serves to guide operators through the entire process of software deployment, device connection, applying for an algorithm license, parameter configuration, unstacking function debugging, and template management.

### 1.1 Interface overview

The overall interface of the AW3 platform is primarily divided into four major functional part: 1. Device Connection Part; 2. Parameter Configuration Part; 3. Display Configuration Part; and 4. Visualization Part. These parts operate independently yet work in synergy, covering the full operational workflow of device access, parameter configuration, visual observation, and algorithm execution (as shown in Figure 1).

![PixPin\_2026-06-01\_10-40-42](https://github.com/user-attachments/assets/caeeab89-9b60-4870-b07d-5ba916cf19e7 )\
_&#x46;igure 1：Interface overview_



## 2. Display Configuration Part

Interface & Language Settings: Used to configure the real-time display type and system language of the software interface. Parameters take effect immediately without requiring additional saving or distribution, adapting to various configuration and observation scenarios.

![PixPin\_2026-06-04\_08-11-06](https://github.com/user-attachments/assets/57c2c6c0-4204-4f63-a526-5335641bb869 )\
_&#x46;igure 2: Display Configuration_



## 3. Visualization Part

![PixPin\_2026-06-04\_08-13-07](https://github.com/user-attachments/assets/0f069992-8a27-4bd3-bdb0-3aedfbc3bf62 )\
_&#x46;igure 3: Visualization_



## 4. Parameter Configuration Part

### 4.1 Device Connection tab

When clicking the Device Connection tab, the content will then be at the right side of the displays, as shown in Figure 4 red box. The information of the centers AlgPlatformViewer has detected will be displayed under the [Discover Centers] button. 

* Center Address: The IP address of the center that AlgPlatformViewer is connected to.
* Center Port: The port number used by the center to transport all operational data streams. This includes sharing information about cameras connected to this center with other centers, as well as importing real-time 3D image data from cameras.
* Broadcast Address: Defaults to "auto". In this mode, the center automatically broadcasts its IP address and Discovery Port information via a UDP packet.
* Discovery Port: The port number used by the center to broadcast its IP address and port details to other centers within the same subnet. When a center receives a discovery packet from another center, it sends a response. This mechanism allows centers to discover each other and establish collaboration.
* Timeout Value: The timeout duration in milliseconds (ms). This defines how long AlgPlatformViewer will attempt to connect to the center before stopping if a connection cannot be established.
* [Discover Centers]: Clicking this button detects all centers on the same subnet and displays them below, and AlgPlatformViewer will automatically connect to the first center in the list. By clicking a center in the list, all virtual cameras created by that center will then appear in the Device Connection Part. You can switch to a specific virtual camera's view in the Visualization Part by clicking the virtual camera number.


![PixPin\_2026-06-02\_08-32-02](https://github.com/user-attachments/assets/7e4dc5e0-3f76-4535-a265-ec2f6339c8de )\
_&#x46;igure 4：Connect to center_


* [Connect center]: By clicking this button, the AlgPlatformViewer will manually connect to a selected center. This is for the case if the subnet routing doesn't support UDP broadcast discovery.

### 4.2 Create an virtual camera

When a computing board is connected to an camera, you need to create a corresponding virtual camera for it. 

* Go to the "Device Connection" interface and click [Create Virtual Camera] at the bottom. A creation window will pop up.

![PixPin\_2026-06-02\_08-32-02](https://github.com/user-attachments/assets/c21a987d-1778-483b-9bfb-a5204c68f04b )\
_&#x46;igure 5：Create Virtual Camera_

* In the window, enter the "Camera Name" and click [Search Physical Cameras]. Select the target camera from the search results and click [Add Selected] to add it to the "Base Cameras managed by the virtual camera" on the right side.
  
* Select the target Base Camera under "Base Cameras managed by the virtual camera" and click [Create Virtual Camera] to complete the setup. The newly created virtual camera will appear in the virtual camera list on the left, ready for subsequent connection and operation.

![PixPin\_2026-06-02\_08-32-02](https://github.com/user-attachments/assets/6feedd18-a414-40fb-95f1-9d865c2af870 )\
_&#x46;igure 6：Add real cameras_



### 4.3 Depalletizing

The Depalletizing Configuration Interface is a core feature of the PalletEye algorithm. It integrates task template/mode settings, algorithm parameter configuration, and core operational capabilities. Designed to support parameter configuration, calibration, task template management, and algorithm computation for soft-pack and carton depalletizing scenarios, it is fully adapted to the demands of routine industrial operations and on-site tuning.

![PixPin\_2026-06-03\_08-14-13](https://github.com/user-attachments/assets/ed7ae923-93b9-4c40-92eb-f2922a351392 )\
_&#x46;igure 7：Depalletizing Configuration_


#### 4.3.1 Choose Template and Mode

1. [Fetch Current Parameters]: By clicking this button, the AlgPlatformViewer fetches all the Global-, Region-, and Calibration parameters saved on the center connected. The fetched parameters are then loaded into the Global-, Calibration-, Region settings for visualization and further configuration if needed.
2. Template Selection: Select saved Global settings template via a dropdown menu for quick switching between scenario-specific configurations, such as for different shapes of bags.
3. Material Type Switching: Supports switching between two material types—Bag (Soft-pack) and Box (Carton)—to adapt to different depalletizing target detection logics.
4. [Apply Calibration to All Templates and Distribute]: This button applies the Region and Calibration settings to all other templates. The logic is that Global settings contain parameters specific to a depalletizing target, which may change when bag/box types change. However, the detection area and camera calibration remain constant since the robot's physical position does not change. Therefore, when the bag/box type changes, you only need to update the Global settings, without having to re-enter the Region and Calibration parameters every time.

![PixPin\_2026-06-03\_08-18-31](https://github.com/user-attachments/assets/a95f69b7-ed94-4d1b-a54e-671be46469b6 )\
_&#x46;igure 8：Choose template and mode_




#### 4.3.2 Global Settings

The Global Settings defines the core filtering and detection parameters for depalletizing target detection. It is used to control bag/box detection accuracy and filtering rules. The parameters are described as follows:

1. Aspect ratio threshold: Determines the reasonable range for the length-to-width ratio of flexible packages. It is recommanded to use the default value. 
2. Fill Ratio: Determines the threshold of how well the detected target fills the detection frame. Recommended value is 0.7. Bag/box with a fill ratio lower than this threshold will be filtered out to avoid invalid or interfering targets.
3. Standard Dimensions (L x W mm): Sets the standard length and width benchmarks for the target material.
4. Length/Width Range (mm): Defines the valid length and width intervals for bag/box. Targets falling outside these ranges are automatically filtered. For the bag/box length, Leave approx. 25% margin at the limit, based on actual bag/box length. For the bag/box width, Leave approx. 20% margin at the limit, based on actual bag/box width.
5. Layer Height (mm): This parameter is used to filter bag/box by layer height and distinguish items across different stacking levels. Since the robot picks only one bag from the top of the stack at a time, bags in the second layer and all layers below will be filtered out from further computation. We recommend setting the layer height to 0.6 times the actual bag/box height.
6. Arrangement: Defines the priority order for the algorithm to detect bag/box. It defaults to "Near to far," meaning the system prioritizes detecting the nearest bag/box first. This setting is crucial in industrial environments where bag/box may not be stacked neatly, and items on the same layer might partially overlap. This function prevents the system from attempting to pick up a top layer bag/box that has another item partly on top of it, which could cause displacement or instability during retrieval. For example in Figure 9, you can see the arrangement order as the green number. Keep this setting as default. 
7. Enable merge: Merges the same package that was incorrectly split into multiple parts due to wrinkles on the stacked packages. Default: Disabled. Enable this only when a single package is mistakenly split into two.
8. Enable PCA Pose Calculation: Ensures stable positioning when there are voids (missing data) in the point cloud. Default: Keep the default settings.
9. Enable Transition Points: Moves the robotic arm to a transition point directly above the package before grasping. Enable based on your specific requirements.
10. Transition Point Extension Distence: The height of the transition point above the package. Recommendation: Set to 1.5 times the thickness of the package.

![PixPin\_2026-06-03\_08-19-04](https://github.com/user-attachments/assets/0ebbb23f-5983-4be9-833f-8e9ec71ea282 )\
_&#x46;igure 9：Global Settings_




If the bag/box's volume and size exceed the maximum Length/Width range in the Global settings, or if the target bag/box is too small and falls below the minimum Length/Width range, the system will filter out the bag/box and will not detect it as a target. This is shown in Figure 8. If that happened, switch template or change Global settings parameters, and then click [Save and Send], and then [Single trigger].

![PixPin\_2026-06-03\_09-32-28](https://github.com/user-attachments/assets/c73a3fb9-dc2e-48cc-9bde-4498449ceb6f )\
_&#x46;igure 10：Error example_




#### 4.3.3 Safety configuration
Safety parameters are used to configure foreign object detection to prevent personnel or objects from intruding into the grasping area. The parameters and configuration recommendations are detailed in the table below. 

| Parameter | Function | Configuration Recommendation |
| :--- | :--- | :--- |
| Obstacle Size Threshold (mm) | The minimum size used to identify a foreign object. No alarm will be triggered for objects smaller than this value. | Recommended: 30 mm |
| Safety Lift Distance (mm) | Foreign object detection is performed in the space above the current package stack, above this height within the calibrated grasping area. | Recommended: 1.5 times the package thickness. |
| Enable Safety (Obstacle) Detection | Monitors for foreign object intrusion above the package stack. If triggered, the system will stop and issue an alarm. | Default: Disabled. Enable this when safety detection is required. |
     

#### 4.3.4 Region Settings

Used to customize the spatial detection region of the algorithm. By setting the maximum and minimum values for the X, Y and Z, it limits the camera's effective detection space and filters out interfering targets outside the field of detection range.

Note: Before calibration, ensure that the process must be performed with a full stack, and the entire stack must be within the camera's RGB field of view; also region calibration must be re-executed if the position of the camera or robotic arm changes.

![PixPin\_2026-06-03\_08-20-34](https://github.com/user-attachments/assets/1b01b45c-d5a3-49e3-b19f-33c3994839a6 )\
_&#x46;igure 11：Region Settings_




**There are two ways to perform the region calibraion**

**1. Automatic Calibration**
* Click [Region Calibration]. The system will automatically complete the calibration, save and dispatch the settings, and trigger a single detection.
* Check the "Result Point Cloud" to verify whether the region accurately covers the packages on the pallet.
* If the system prompts a calibration failure, please follow the prompts to resolve the issue and try again: For example if the Region is set too small and part of the target bag/box falls outside it, the excluded area will not be counted towards the bag/box's size. If the remaining part inside the region does not meet the minimum Length/Width requirements in the Global Settings, the bag/box will not be detected as a target. This is shown in Figure 12. If that happened, configure the Region Settings and change the region size, then click Save and Send and Single Trigger.

![PixPin\_2026-06-03\_10-27-36](https://github.com/user-attachments/assets/2ebf15b1-32e7-4812-8fc5-0406914438e0 )\
_&#x46;igure 12：Error example_



**2. Manual Calibration**
* Enter values in [Region Configuration] and adjust the bounding box so that the operating area completely covers the flexible packages on the pallet while excluding irrelevant surrounding data.
* Click [Save and Dispatch] to apply the area settings.
* Click [Single Trigger] and check the results in the "Result Point Cloud".




#### 4.3.5 Calibration Settings

Used for fine-tuning and displaying hand-eye calibration parameters between the camera and the robotic arm. Configurable parameters include Euler angles, translation vector, offsets, and the tool coordinate system RT, which serve as the calibration benchmark for depalletizing pose calculations. The initial parameters will automatically be applied to this section after the hand-eye calibration process.

* Euler Angles: Represents the orientation (rotation) of the robotic arm in 3D space. It describes how the robotic arm is tilted or turned using three specific angles: Roll, Pitch, and Yaw.
* Translation Vector: Represents the position of the robotic arm in 3D space. It defines the robotic arm's exact location relative to a reference point (origin) using X, Y, and Z coordinates. It tells the system how far the tool tip is from the robot camera in the length, width, and height directions.
* Offset: Represents an intentional adjustment or shift applied to a target position. It adds a specific distance to the original coordinates to fine-tune the final location (e.g., to avoid collisions or adjust a gripping point).
* Tool frame R: It displays the X, Y, and Z distances from the robot's end flange to the robot's gripper tool.
* Tool frame T: It specifies the rotational angles (expressed in Euler angles: Rx, Ry, Rz) of the tool relative to the robot's end flange.

![PixPin\_2026-06-03\_08-20-11](https://github.com/user-attachments/assets/bc8e03b4-efba-4134-8a72-c49b4a901501)\
_&#x46;igure 13：Calibration Settings_



#### 4.3.6 Hand-eye calibration

* [Add point]: Enter the X, Y, and Z value of the teaching point into the input box and click the [Add Point] button to add the point's coordinates to the corresponding coordinate area.
* [Import from Clipboard]: Right-click the RGB display to show the coordinate information of a point in the camera coordinate system. After pasting coordinate data from other devices into the input box, click this button. The system will automatically recognize the format and import the data.
* Camera coordinate area: Displays the coordinates of the four camera teaching points.
* Robot coordinate area: Displays the coordinates of the four robot teaching points.
* [Delete point/Delete all]: Delete a single point or all coordinates in the coordinate area.
* Auto add/Detect markers: When you select the [Auto Add] mode, the hand-eye calibration tool enters auto-add mode. Place a calibration board at the pallet position so that it is fully visible within the camera's field of view. Then, click the [Detect Markers] button. The tool will automatically detect the coordinates of the four corners of the calibration board, eliminating the need to enter them manually.
* [Left handed coordinate system]: Check this option to switch the coordinate area to a left-handed coordinate system.
* [Calibration]: Click the [Calibration] button to start the hand-eye calibration.

[Gripper tool offset] section
* Euler angles: Enter the Euler angles for the robot gripper tool (e.g., the robot wrist).
* Offset: Enter the offset values for the robot gripper tool.
* Camera teaching point coordinates/Robot teaching point coordinates: These sections are primarily used to verify calibration results. By entering a point coordinate from the camera coordinate area, the system will automatically transform it into the corresponding robot coordinate, which will then be displayed in the Robot Teaching Point Coordinates section.

**Why is hand-eye calibration necessary?** 

In practical applications, robots need to combine visual information to execute tasks. The robotic arm operates within its own coordinate system and knows its exact position and orientation (e.g., XYZ values and angles) within it. Similarly, the camera operates within its own coordinate system, with the optical center serving as the origin, and it knows the position and orientation of the target object relative to its lens. However, the camera system does not know its spatial pose relative to the robot's base. This means it can only determine coordinates within its own system and cannot directly map them to the robot's coordinate system.

Hand-eye calibration is designed to establish the coordinate transformation matrix between the "eye" and the "hand". Only after this step is completed can the robot accurately translate the 3D point cloud coordinates captured by the camera into control coordinates that the robotic arm can understand and execute, thereby achieving true "eye-to-hand" coordination.


**Automated hand-eye calibration**
1. Install the calibration needle on the Z-axis extension line of the robot arm flange. Place the calibration board steadily on the surface where the bags are stacked (e.g., the floor or pallet), ensuring it is unobstructed and centered within the camera's field of view.
2. In the "Camera Coordinate Area" on the right side of the interface, click [Detect Markers]. The system will automatically capture the four feature points and record their camera coordinates.
3. First, check the sequence of the feature points in the "Result RGB" image on the main interface. Then, move the robot arm and use the calibration needle to precisely touch each feature point in that exact sequence. After touching each point, enter the corresponding robot arm coordinates in the "Robot Coordinate Area" in X, Y, Z format (separated by commas) and click [Add Point]. After successfully collecting all four points, click [Calibrate] to allow the system to automatically calculate the hand-eye matrix.
4. Check the calibration error in the "Calibration Error" section at the bottom right of the interface. The calibration is considered successful if the maximum error is within the acceptable range (less than 15 mm). If the error is too large, check whether the calibration board has shifted or if the needle touches were inaccurate, and repeat the process.

![PixPin\_2026-06-03\_08-18-31](https://github.com/user-attachments/assets/d96c0cd3-ba91-47d9-bce3-2fef00c7a10d)\
_&#x46;igure 14: Automatic Hand-Eye Calibration_

![PixPin\_2026-06-03\_08-18-31](https://github.com/user-attachments/assets/43c9a454-10af-41e3-9b31-e86e336ae06a )\
_&#x46;igure 15: Calibration error_






**Manual hand-eye calibration**
1. Install the calibration needle on the Z-axis extension line of the robot arm flange. Place the checkerboard steadily on the surface where the bags are stacked (e.g., the floor or pallet), ensuring it is unobstructed and centered within the camera's field of view.
2. In the "Normal RGB" image on the main interface, right-click a corner point of the checkerboard to copy its coordinates. Then, navigate to the "Camera Coordinate Area" in the hand-eye calibration interface and paste the camera coordinates (in X, Y, Z format, separated by commas) from the clipboard. Click [Add Point].
3. Operate the robot arm to touch the exact same corner point with the calibration needle (it is recommended to touch the intersection of the black and white squares for maximum precision). Manually enter the robot arm coordinates for this point in the "Robot Coordinate Area" in X, Y, Z format (separated by commas) and click [Add Point]. Repeat this procedure from four different orientations, ensuring that the robot coordinates correspond one-to-one with the sequence of feature points in the "Camera Coordinate Area". After collecting all four points, click [Calibrate].
4. Check the results in the "Calibration Error" section at the bottom right of the interface: the calibration is successful if the error is within the acceptable range (less than 15 mm). If the error is too large, please check whether the checkerboard is clearly visible and if the needle touches were accurate, then recalibrate.

![PixPin\_2026-06-03\_08-18-31](https://github.com/user-attachments/assets/0381f3b9-d974-4fc8-afec-33278a306322 )\
_&#x46;igure 16: Manual hand-eye calibration_




**Fixed Deviation Correction Example**
Because a calibration needle is used during the hand-eye calibration process, there is typically a fixed XYZ and angular offset between the suction cup and the needle. Therefore, this deviation must be compensated for in this step.

1. Place a soft gripper on the pallet and manually jog the robot arm into the grasping pose. Record the robot's current pose from the robot coordinate system.
2. Move the robot arm away while keeping the soft gripper in its original position. Manually trigger the camera to capture an image, and obtain the algorithm generated grasping pose from [Result log] tab, which has already been transformed into the robot coordinate system.
3. Calculate the fixed offset between these two poses. Enter the compensation values into the "Euler Angles" and "Translation Vector" fields under "Calibration Configuration" to complete the correction.

![PixPin\_2026-06-03\_08-18-31](https://github.com/user-attachments/assets/5badda38-7044-4ee8-a809-fe408b918f66 )\
_&#x46;igure 17: Fixed Deviation Correction Example_



#### 4.3.7 Depalletizing Buttons

1. [Single trigger]: Click the button to execute a single image capture and depalletizing calculation. It updates detection results (such as bag/box grasping pose and dimensions) in real-time, suitable for single-run debugging and verification.
2. Add Template/Delete template:

* [Add template]： Click the button and enter a custom name to create and save a new template.
* [Delete Current Template]: One-click deletion of the currently selected template to clear invalid scene configurations.

3. [Region calibration]: Click the button to execute the region calibration. The algorithm identifies all bag/box targets within the RGB field of view, selects the most centered bag/box as the base detection area, expands outward by a fixed range, and generates the valid detection area with a visual display of the calibration result.
4. [Hand-eye calibration]: During the initial setup, clicking this button will launch the hand-eye calibration tool. The purpose of this tool is to align the separate coordinate systems of the camera and the robot arm. The "Camera Coordinate" section displays the X, Y, Z value of a specific point within the camera's coordinate system showing the camera's location. Below this, an RGB image shows four reference points on the tray. You need to move the robot arm's tip to each of these points and input the corresponding coordinates into the "Robot Coordinate" section. Once you click OK, the algorithm will unify the camera's and robot arm's coordinate systems, determining the precise spatial relationship between them.
5. [Save and send]: Saves and deploys all current template parameters (detection, calibration, and area configurations) to the camera device. Parameters are persisted and will not be lost after a device restart.

![PixPin\_2026-06-03\_08-21-01](https://github.com/user-attachments/assets/4d7dcb14-2298-4e11-a79e-3f79b4b49614)\
_&#x46;igure 18: Buttons_



## 5. Deployment process

This chapter provides a complete deployment configuration process for the AW3 platform combined with the PE flexible packaging depalletizing algorithm. It serves as a reference for standardized on-site configuration and is applicable to scenarios such as initial deployment of new machines, site relocation, and bag/box template resets.

#### Step 1: Launch the Software

Open AlgPlatformViewer.exe to run the AW3 host software.

#### Step 2: Verify Network Environment

Ensure that the host computer and the camera algorithm module are on the same local area network (LAN) subnet to guarantee normal communication, discovery, and connection of the devices. For more details about IP and Firewall configuration, please refer to the LxCameraViewer user manual at https://github.com/Lanxin-MRDVS/CameraSDK/wiki/LxCameraViewer-User-Manual

#### Step 3: Change IP address and create virtual cameras in case of dual connection

When a single computing board is connected to two cameras simultaneously, the IP address of one camera must be modified (to avoid a conflict with the other), and a corresponding virtual camera must be created for it (refer to Appendix B for instructions on IP modification and virtual camera creation). The two cameras operate as independent units; consequently, all subsequent processes—including parameter configuration and deployment—must be executed separately for each camera.


#### Step 4: Connect to the Device

After the device starts, return to the \[Device Connection] interface. Click the \[Discover centers] button to refresh the LAN connection as shown Figure 19 in red box. Select the center to which your desired camera is connected from the device list as shown in red box, click it, and camera options connected to that center will display on the left of the screen as shown in Figure 19 red box. Click on the virtual camera option and click the camera with which you want to establish a connection.


![PixPin\_2026-06-29\_05-43-36](https://github.com/user-attachments/assets/92f56b25-c362-47b3-bcc4-afb5aa4dd1bb)\
_&#x46;igure 19: Discover centers_


#### Step 5: Activate Algorithm Authorization

Switch to the [Algorithm enable] tab, select the Soft-bag Depalletizing algorithm, click [Algorithm Authentication] button, and obtain the authorization request key by clicking [Get request key]. Submit this key to the MRDVS FAE personnel to apply for a formal License. Once received, paste the authorization key into the License input box and click [Apply License] to activate the algorithm.

![PixPin\_2026-06-04\_05-43-36](https://github.com/user-attachments/assets/b945a501-ddea-4493-bfdb-e3294c2dfb3a)\
_&#x46;igure 20: Activate algorithm_


![PixPin\_2026-06-04\_05-43-36](https://github.com/user-attachments/assets/adab5051-2423-47c8-87ab-000e9d1d40e4 )\
_&#x46;igure 21: Get request key_


#### Step 6: Configure Basic Camera Parameters

Switch to the Base Camera] tab, select the right camera parameter template matching the business need and camera model at [Template], and click [Send Base Camera settings] to complete the initialization of the camera's parameters. For depalletizing, we recommand [General].

![PixPin\_2026-06-04\_05-48-48](https://github.com/user-attachments/assets/49a371f1-0c9b-4a35-ac92-062218cb5562)\
_&#x46;igure 22: Basic camera parameters_



#### Step 7: Configure Depalletizing Parameters

Enter the [Depalletizing] tab, select the corresponding bag/box template at [Template], then select the [material type] to "Bag" or "box" based on need. Based on the actual volume and size of the on-site bag/box, you can choose the pre-defined [Template] or modify yourself, which will set the Global settings parameters such as standard size, length range, width range, and layer height to adapt to the on-site working conditions.

![PixPin\_2026-06-03\_08-18-31](https://github.com/user-attachments/assets/23fa975a-40f2-47bf-b936-9471ce85770c )\
_&#x46;igure 23: Depalletizing configuration_



#### Step 8: Configure Safety Parameters 

Set the safety parameters to configure foreign object detection and prevent personnel or objects from intruding during the gripping process. 

![PixPin\_2026-06-03\_08-18-31](https://github.com/user-attachments/assets/2f461614-7751-4b74-a4ee-86e0554f16ab )\
_&#x46;igure 24: Safety Parameters_


#### Step 9: Hand-Eye Calibration

Execute the hand-eye calibration process to establish the coordinate alignment between the camera and the robotic arm. Follow the instruction above at [Hand-Eye Calibration] section. Finally, click the [Calibration] button. This will persistently save the calibration parameters to the camera device and automatically apply the [Calibration Settings].

![PixPin\_2026-06-03\_08-18-31](https://github.com/user-attachments/assets/d96c0cd3-ba91-47d9-bce3-2fef00c7a10d )\
_&#x46;igure 25: Hand-Eye Calibration_

#### Step 10: Fixed bias correction

Fine-tune the [Eular angles] and [Translation vector] to correct the XYZ and angle offset. 

![PixPin\_2026-06-03\_08-18-31](https://github.com/user-attachments/assets/34fe9039-d9b0-40e1-9255-d25733b8096d )\
_&#x46;igure 26: Configure fixed bias_


#### Step 11: Region Calibration

By clicking the [Region Calibration] button the software will automatically identify the bag/box within the field of view and generate the valid detection frame, and automatically complete the region calibration. If you want to manually configure the region, remember to click [save and send] button after configuration, to send the new region data to the center.

![PixPin\_2026-06-04\_05-56-00](https://github.com/user-attachments/assets/47886f33-627f-450d-8fac-6cc0c114df53 )\
_&#x46;igure 27: Area calibration_



#### Step 12: Test the result

Click [Single Trigger] to execute a single algorithm detection. Observe the results, including bag/box recognition, grasping pose, and dimension output, to determine whether the detection performance is reasonable and meets the on-site depalletizing requirements. You can also see the results at \[Result log] tab.

#### Step 13: Communication Verification

Request results directly from the algorithm module according to the communication protocol, and observe the corresponding changes on the AW3 interface.

#### Step 14: Efficiency Verification

The latency from sending the request to receiving the result must be less than 2500ms.

## 6. Communication protocol

The system communicates with external devices (e.g., robot arm controllers) via TCP and supports the following two protocol formats. Communication consists of two main parts: external trigger requests and result publishing.

| Protocol Format | Description |
| :--- | :--- |
| **Header/Footer Delimiter Protocol** | Uses custom headers and footers to identify a data frame, with fields separated by delimiters. This format is concise and well-suited for simple text-based interactions. |
| **JSON Protocol** | Utilizes standard JSON format for communication. It can output results such as center coordinates and angles, featuring clear fields and high scalability. |

**Key Configurations:** 
* The trigger port and the result publishing port are configured as two independent items. 
* The timeout duration must be set reasonably based on the maximum execution time of the algorithm. 
* The protocol supports coordinate system transformations (e.g., left-hand vs. right-hand coordinate systems) controlled via parameters.


### 6.1 Architecture Design and Extension Specifications

The communication framework adopts a highly decoupled design for convenient customization:

- Extending Publish Protocols: Inherit the IProtocolPublisher interface, implement the sending logic in the publish method, and register it via the factory class to take effect.

- Extending Trigger Protocols: Inherit the ITriggerProtocol interface to handle listening, request parsing, and calling a unified handler function, eventually encoding and returning the response. This design ensures the protocol layer is completely independent of underlying camera modules, facilitating horizontal replacement.

- Integrating New Algorithms: Supports trigger_only mode, where algorithms execute solely upon receiving external triggers. Algorithms must return a string result, which is distributed by the unified ResultDispatcher. Timeouts return error code -3 by default.

### 6.2 Key Considerations

- Port Separation: The listen_port for receiving triggers and the send_port for actively publishing results are two independent configuration items.

- Timeout Control: timeout_ms governs both the trigger wait time and the TCP publish wait time. In production environments, this should be reasonably configured based on the maximum expected execution time of the algorithm.

- Independent Channels: The UI-side CameraPing uses the gRPC protocol, operating independently from the ResultDispatcher, which exclusively handles result publishing and external triggers.


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
Figure 28: Algorithm error code



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
Figure 29: Package error codes 
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
Figure 30: Status indicators 


## 5.2 Troubleshooting and Adjustments

If recognition or grasping anomalies occur, refer to the table below to locate the corresponding parameters and adjust them as recommended. After making adjustments, click [save and send], and verify the results.

| Parameter | Anomaly / Symptom | Recommended Adjustment |
| :--- | :--- | :--- |
| **Standard Size / Length & Width Range** | Normal soft bags are incorrectly filtered out. | Widen the range appropriately, or reset it based on the actual dimensions of the soft bags. |
| **Enable Merging** | A single bag is mistakenly split into two. | Enable the merging function. |
| **Enable Transition Points / Transition Point Extension Distance** | Grasping causes scraping/collision with the bag, or the cycle time is too slow. | Enable transition points. If scraping occurs, increase the extension distance; if the cycle time is too slow, decrease it. |
| **Calibration Area** | Target bags are filtered out, or surrounding debris is mistakenly selected. | Move the pallet stack to the center of the area, or recalibrate the area. |
| **Safety Detection Parameters** | Foreign objects above fail to trigger an alarm, or irrelevant objects cause false alarms. | For missed detections: Enable safety detection or decrease the occlusion size threshold. For false alarms: Increase the size threshold or raise the distance threshold. |
