## Instruction

AwareSight3 （or so called AW3） is an application management platform designed for industrial vision algorithms. It is responsible for device connection, authentication, camera parameter configuration, and the management and deployment of algorithm parameters. PalletEye （so called PE） is a built-in algorithm module within the platform, specifically tailored for soft bag and carton unstacking. Leveraging RGB-D camera data, it delivers capabilities such as pallet cargo recognition, region calibration, hand-eye calibration, grasp pose estimation, and dimension detection. It is widely applied in industrial pallet unstacking scenarios. This manual serves to guide operators through the entire process of software deployment, device connection, apply for algorithm license, parameter configuration, unstacking function debugging, and template management.


## Interface overview

The overall interface of the AW3 platform is primarily divided into four major functional sections: 1. Connection Management Section; 2. Parameter Configuration Section; 3. Display Configuration Section ; and 4. Visualization Section. These sections operate independently yet work in synergy, covering the full operational workflow of device access, parameter configuration, visual observation, and algorithm execution (as shown in Figure 1).

<p align= “center”>
<img alt="PixPin_2026-06-01_10-40-42" src="https://github.com/user-attachments/assets/ad3c08cf-d85c-40c1-b935-9b1b1934ab76" />
<br>
   <em> Figure 1：Interface overview </em>
</p>

## Parameter Configuration Section

The Parameter Configuration Section contains five menus, the Device Connection, the Algorithm enable, the Parameters, the Soft-pack depalletizing, and the Result log. 

## Device Connection menu

When clicking the Device Connection menu, the content will then be at the right side of the displays, as shown in Figure 2 red box. The Center Connection section shows the information of the center AlgPlatformViewer is connected to. 

- Center Address: The IP address of the center that AlgPlatformViewer is connected to.
- Center Port: The port number used by the center to transport all operational data streams. This includes sharing information about cameras connected to this center with other centers, as well as importing real-time 3D image data from cameras.
- Broadcast Address: Defaults to "auto". In this mode, the center automatically broadcasts its IP address and Discovery Port information via a UDP packet.
- Discovery Port: The port number used by the center to broadcast its IP address and port details to other centers within the same subnet. When a center receives a discovery packet from another center, it sends a response. This mechanism allows centers to discover each other and establish collaboration.
- Timeout Value: The timeout duration in milliseconds (ms). This defines how long AlgPlatformViewer will attempt to connect to the center before stopping if a connection cannot be established.
- Discover Centers: Clicking this button detects all centers on the same subnet and displays them in below, and AlgPlatformViewer will automatically connect to first center in order. By clicking a center in the list, all virtual cameras created by that center will then appear in the Connection Management section. You can switch to a specific virtual camera's view in the Display section by clicking the virtual camera number.

(Virtual cameras are designed to support multi-camera cooperation in the future. Currently, each virtual camera is only mapped to a single physical camera.)

<p align= “center”>
<img alt="PixPin_2026-06-02_08-32-02" src="https://github.com/user-attachments/assets/36f48856-18df-491d-9da3-2466a98f3fc8" />
<br>
   <em> Figure 2：Center Connection </em>
</p>


- Connect center: By clicking this button, the AlgPlatformViewer will manually by conneted to a selected center. This is for the case if the subnet routing doesn't support UDP broadcast discovery.  

## Soft-pack depalletizing

The Soft-pack Depalletizing Configuration Interface is a core feature of the PalletEye algorithm. It integrates task template/mode settings, algorithm parameter configuration, and core operational capabilities. Designed to support parameter configuration, calibration, task template management, and algorithm computation for soft-pack and carton depalletizing scenarios, it is fully adapted to the demands of routine industrial operations and on-site tuning.

<p align= “center”>
<img alt="PixPin_2026-06-03_08-14-13" src="https://github.com/user-attachments/assets/8a8d5f4b-1c5b-426d-b8ee-d078f8e8ffd1" />
<br>
   <em> Figure 3：Soft-bag depalletizing </em>
</p>

### Choose Template and Mode
1. Fetch Current Parameters: By clicking this button, the AlgPlatformViewer fetches the soft-bag parameters and the pre-defined template parameters from the center. The fetched parameters are then loaded into the Global-, Calibration-, Region settings for visualization and further configuration if needed.

2.Template Selection: Selects saved Global settings template via a dropdown menu for quick switching between scenario-specific configurations, such as for different shapes of bags

3. Material Type Switching: Supports switching between two material types—Soft-pack (Bag) and Carton (Box)—to adapt to different depalletizing target recognition logics.

4. Apply Calibration to All Templates and Distribute: This button applies the Region and Calibration settings to all other templates. The logic is that Global settings contain parameters specific to a depalletizing target, which may change when cargo types change. However, the detection area and camera calibration remain constant since the robot's physical position does not change. Therefore, when the cargo type changes, you only need to update the Global settings, without having to re-enter the Region and Calibration parameters every time.

5. Operation Mode Switching: Simple Mode: Parameters are fixed. It performs only basic validation on cargo dimensions without advanced algorithm features, making it suitable for standardized, routine depalletizing scenarios. Expert Mode: Unlocks full custom parameter configuration and enables advanced features like parcel merging. This mode is designed for complex working conditions and scenarios requiring refined recognition (UI to be continuously optimized).

<p align= “center”>
<img alt="PixPin_2026-06-03_08-18-31" src="https://github.com/user-attachments/assets/9ac618ee-a4be-4569-babb-f97960a7bbfc" />
<br>
   <em> Figure 4：Choose template and mode </em>
</p>

### Global Settings

The Global Settings defines the core filtering and recognition parameters for depalletizing target detection. It is used to control cargo detection accuracy and filtering rules. The parameters are described as follows:

1. Fill Ratio: Determines the threshold of how well the detected target fill the detection frame. Recommended value is 0.7. Cargo with a fill ratio lower than this threshold will be filtered out to avoid invalid or interfering targets.

2. Standard Dimensions (L x W mm): Sets the standard length and width benchmarks for the target material.

3. Length/Width Range (mm): Defines the valid length and width intervals for cargo. Targets falling outside these ranges are automatically filtered.

4. Layer Height (mm):  This parameter is used to filter cargo by layer height and distinguish items across different stacking levels. For example, if the Layer Height is set to 200 mm, it means that when soft-bags are stacked, the height of a single bag (e.g., 200 mm) determines the height of each layer. Since the robot picks only one bag from the top of the stack at a time, bags in the second layer and all layers below will be filtered out from futher computation.

5. Arrangement Order: Defines the priority order for the algorithm to recognize cargo. It defaults to "Near to far," meaning the system prioritizes recognizing the nearest cargo first. This setting is crucial in industrial environments where cargo may not be stacked neatly, and items on the same layer might partially overlap. This function prevents the system from attempting to pick up a top layer cargo that has another item partly on top of it, which could cause displacement or instability during retrieval.

6. Advanced Toggles [Under Development]: Includes options for enabling large-size splitting, parallel alignment correction, multiple results at once, and occlusion detection. In the current version, these are reserved configuration items and are not yet active.



<p align= “center”>
<img alt="PixPin_2026-06-03_08-19-04" src="https://github.com/user-attachments/assets/39a12f80-453a-4253-81d5-8497591b3fed" />
<br>
   <em> Figure 5：Clobal Settings </em>
</p>


### Region Settings

Used to customize the spatial detection range of the algorithm. By setting the maximum and minimum values for the X, Y and Z, it limits the camera's effective recognition space and filters out interfering targets outside the field of detection frame. 

<p align= “center”>
<img alt="PixPin_2026-06-03_08-20-34" src="https://github.com/user-attachments/assets/422ed648-a506-43c8-a68f-87bbdc06a61e" />
<br>
   <em> Figure 6：Region Settings </em>
</p>

### Output Settings [Under Development]

All configuration options in this section are currently under development, and settings are not yet active; the interface is reserved for future use, including Euler angle type, RZ range, Reverse range, Output type (3D/2D), rxry tilt range, Output unit (deg/mm), Output precision. 

<p align= “center”>
<img alt="PixPin_2026-06-03_08-19-45" src="https://github.com/user-attachments/assets/3dd318a9-3277-48a6-87f8-c64dfab89143" />
<br>
   <em> Figure 7：Output Settings </em>
</p>

### Calibration Settings

Used for managing hand-eye calibration parameters between the camera and the robotic arm. Configurable parameters include Euler angles, translation vector, offsets, and the tool coordinate system RT, which serve as the callibration benchmark for depalletizing pose calculations. 
Used for initial calibration. 

- Euler Angles: Represents the orientation (rotation) of an object in 3D space. It describes how an object is tilted or turned using three specific angles: Roll, Pitch, and Yaw. 

- Translation Vector: Represents the position of an object in 3D space. It defines the object's exact location relative to a reference point (origin) using X, Y, and Z coordinates. It tells the system how far the tool tip is from the robot camera in the length, width, and height directions.

- Offset: Represents an intentional adjustment or shift applied to a target position. It adds a specific distance to the original coordinates to fine-tune the final location (e.g., to avoid collisions or adjust a gripping point).

<p align= “center”>
<img alt="PixPin_2026-06-03_08-20-11" src="https://github.com/user-attachments/assets/bc8e03b4-efba-4134-8a72-c49b4a901501" />
<br>
   <em> Figure 8：Calibration Settings </em>
</p>

### Buttons

1. Single trigger: Click the button to execute a single image capture and depalletizing calculation. It updates detection results (such as cargo grasping pose and dimensions) in real-time, suitable for single-run debugging and verification.

2. Add Template/Delete template: 
- Add template： Click the button and enter a custom name to create and save a new template.
- Delete Current Template: One-click deletion of the currently selected template to clear invalid scene configurations. 

3. Region calibration: Click the button to execute the region calibration. The algorithm identifies all cargo targets within the RGB field of view, selects most centered cargo as the base detection area, expands outward by a fixed range, and generates the valid detection area with a visual display of the calibration result. 

4. Hand-eye calibration: Currently, this feature only supports the Chinese version. During the initial setup, clicking this button will launch the hand-eye calibration tool. The purpose of this tool is to align the separate coordinate systems of the camera and the robot arm.
The "Camera Coordinate" section displays the X, Y, Z value of a specific point within the camera's coordinate system showing the camera's location. Below this, an RGB image shows four reference points on the tray. You need to move the robot arm's tip to each of these points and input the corresponding coordinates into the "Robot Coordinate" section. Once you click OK, the algorithm will unify the camera's and robot arm's coordinate systems, determining the precise spatial relationship between them. 

5. Save and send: Saves and deploys all current template parameters (detection, calibration, and area configurations) to the camera device. Parameters are persisted and will not be lost after a device restart.

<p align= “center”>
<img alt="PixPin_2026-06-03_08-21-01" src="https://github.com/user-attachments/assets/4d7dcb14-2298-4e11-a79e-3f79b4b49614" />
<br>
   <em> Figure 9：Buttons </em>
</p>


## Connection Management Section


## Display Configuration Section

Interface & Language Settings: Used to configure the real-time display type and system language of the software interface. Parameters take effect immediately without requiring additional saving or distribution, adapting to various debugging and observation scenarios.


## Visualization Section

## Overrun 
