# Instruction

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
<img width="1437" height="906" alt="PixPin_2026-06-02_08-32-02" src="https://github.com/user-attachments/assets/36f48856-18df-491d-9da3-2466a98f3fc8" />
<br>
   <em> Figure 2：Center Connection </em>
</p>


- Connect center: By clicking this button, the AlgPlatformViewer will manually by conneted to a selected center. This is for the case if the subnet routing doesn't support UDP broadcast discovery.  

## Soft-pack depalletizing

The Soft-pack Depalletizing Configuration Interface is a core feature of the PalletEye algorithm. It integrates task template/mode settings, algorithm parameter configuration, and core operational capabilities. Designed to support parameter configuration, calibration, task template management, and algorithm computation for soft-pack and carton depalletizing scenarios, it is fully adapted to the demands of routine industrial operations and on-site tuning.

### Task Template and Mode
1. Fetch Current Parameters: By clicking this button, the AlgPlatformViewer fetches the soft-bag parameters and the pre-defined template parameters from the center. The fetched parameters are then loaded into the Global-, Calibration-, Region settings for visualization and further configuration if needed.

2.Template Selection: Selects saved Global settings template via a dropdown menu for quick switching between scenario-specific configurations, such as for different shapes of bags

3. Material Type Switching: Supports switching between two material types—Soft-pack (Bag) and Carton (Box)—to adapt to different depalletizing target recognition logics.

4. Apply Calibration to All Templates and Distribute: This button applies the parameters of the selected Global settings template to the region calibration and hand-eye calibration. The calibration results are then updated in the calibration and region settings template.

5. Operation Mode Switching: Simple Mode: Parameters are fixed. It performs only basic validation on cargo dimensions without advanced algorithm features, making it suitable for standardized, routine depalletizing scenarios. Expert Mode: Unlocks full custom parameter configuration and enables advanced features like parcel merging. This mode is designed for complex working conditions and scenarios requiring refined recognition (UI to be continuously optimized).

### Global Settings

The Global Settings defines the core filtering and recognition parameters for depalletizing target detection. It is used to control cargo detection accuracy and filtering rules. The parameters are described as follows:

1. Fill Ratio: Determines the threshold of how well the detected target fill the detection frame. Recommended value is 0.7. Cargo with a fill ratio lower than this threshold will be filtered out to avoid invalid or interfering targets.

2. Standard Dimensions (L x W mm): Sets the standard length and width benchmarks for the target material.

3. Length/Width Range (mm): Defines the valid length and width intervals for cargo. Targets falling outside these ranges are automatically filtered.

4. Layer Height (mm):  This parameter is used to filter cargo by layer height and distinguish items across different stacking levels. For example, if the Layer Height is set to 200 mm, it means that when soft-bags are stacked, the height of a single bag (e.g., 200 mm) determines the height of each layer. Since the robot picks only one bag from the top of the stack at a time, bags in the second layer and all layers below will be filtered out from futher computation.

5. Arrangement Order: Defines the priority order for the algorithm to recognize cargo. Set to Near to far as default, which means the system recognizes near cargos first, and then far cargos. ????

6. Advanced Toggles [Under Development]: Includes options for enabling large-size splitting, parallel alignment correction, multiple results at once, and occlusion detection. In the current version, these are reserved configuration items and are not yet active.
Interface & Language Settings

7. Used to configure the real-time display type and system language of the software interface. Parameters take effect immediately without requiring additional saving or distribution, adapting to various debugging and observation scenarios.

### Region Settings

### Calibration Settings

## Connection Management Section


## Display Configuration Section

## Visualization Section
