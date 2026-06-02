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

### Device Connection menu

When clicking the Device Connection menu, the content will then be at the right side of the displays, as shown in Figure 2 red box. The Center Connection section shows the information of the center AlgPlatformViewer is connected to. 

- Center Address: The IP address of the center that AlgPlatformViewer is connected to.
- Center Port: The port number used by the center to transport all operational data streams. This includes sharing information about cameras connected to this center with other centers, as well as importing real-time 3D image data from cameras.
- Broadcast Address: Defaults to "auto". In this mode, the center automatically broadcasts its IP address and Discovery Port information via a UDP packet.
- Discovery Port: The port number used by the center to broadcast its IP address and port details to other centers within the same subnet. When a center receives a discovery packet from another center, it sends a response. This mechanism allows centers to discover each other and establish collaboration.
- Timeout Value: The timeout duration in milliseconds (ms). This defines how long AlgPlatformViewer will attempt to connect to the center before stopping if a connection cannot be established.
- Discover Centers: When this button is clicked, all centers connected to the same subnet will be detected and displayed in the list below.

<p align= “center”>
<img width="1437" height="906" alt="PixPin_2026-06-02_08-32-02" src="https://github.com/user-attachments/assets/36f48856-18df-491d-9da3-2466a98f3fc8" />
<br>
   <em> Figure 2：Center Connection </em>
</p>


- Connect center
- Fetch virtual cameras

### Algorithm enable menu




## Connection Management Section


## Display Configuration Section

## Visualization Section
