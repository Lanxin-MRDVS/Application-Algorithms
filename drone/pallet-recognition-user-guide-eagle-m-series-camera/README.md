
# 1. Introduction 

Pallet recognition is a solution developed by MRDVS using the in-house developed Eagle-M series cameras. 
It's is designed for forklifts to seamlessly docking pallets. 
The system boasts adaptive compatibility with a range of pallet specifications, 
eliminating the need for specific configurations. With dynamic detection capabilities,
it can identify structures on the go, eliminating the requirement for the vehicle to come to a complete stop.
The system is versatile, supporting recognition in diverse scenarios like floor-to-floor transitions, storage locations, and shelves.
Adaptive Pallet Recognition, The system can adaptively recognize pallets of different specifications, 
including wooden and plastic pallets with different shapes, as shown below.


<p align="center">
<img  alt="Picture3" src="https://github.com/user-attachments/assets/07ea19b2-275a-4697-bbbe-932926c33afc" />
<br>
  <em></em>
</p>


<p align="center">
<img  alt="Picture2" src="https://github.com/user-attachments/assets/b9e6997f-2853-4967-94bb-2f980dbd7ac4" />
<br>
  <em></em>
</p>

<p align="center">
<img  alt="Picture5" src="https://github.com/user-attachments/assets/4e9ed2c6-5b31-4dd9-8c6d-b36cdfb230d8" />
<br>
  <em></em>
</p>

<p align="center">
<img  alt="Picture4" src="https://github.com/user-attachments/assets/7c750174-1cc7-45d8-b5ab-2b93efc2f910" />
<br>
  <em></em>
</p>

# 2. Eagle-M camera installation

As shown in the figure below, install the Eagle-M camera at a distance of 35cm to 45cm above the base panel 
of the fork arm, ensuring it is close to the center of the two fork teeth (with a left-right deviation of 
no more than 5cm).

<p align="center">
<img width="50%" height="50%" alt="Näyttökuva 2026-06-08 kello 11 00 12" src="https://github.com/user-attachments/assets/6c61370b-6d9f-4b9c-8b46-5ddc8fbfb13a" />
<br>
  <em>Figure 1: Installation example</em>
</p>

# Interfaces

## Main Interface

After launching the software, the main interface shown below will appear. You can perform operations such as camera connection, camera calibration, and pallet recognition on this screen.

<p align="center">
<img alt="PixPin_2026-06-09_12-18-31" src="https://github.com/user-attachments/assets/d70a5468-f972-4d3c-86bd-e2aac69758ca" />
<br>
  <em>Figure 2: Main Interface</em>
</p>

The interface includes the following functions: 

| Function Module | Specific Functions/Description |
| :--- | :--- |
| Menu Bar | Includes basic operations, advanced applications, extrinsic calibration, camera operations, advanced parameters, and save parameters |
| Camera Parameter Settings | Includes scanning, embedded mode, camera on/off, real-time display, detection, projection, and camera calibration parameter settings |
| File Import | Includes calibration parameter files, recognition images, and folders |
| Log Printing | Prints detection results, camera firmware version, algorithm version, etc. |
| Image Display | Displays image dat



## Advanced applications Interface


Camera configuration file: The camera configuration file "pallet_settings.json", which contains the camera parameters, will be downloaded and loaded into PalletPro.

Camera IP/ID: Displays the IP address and ID of the connected camera.

| Parameter | Value/Status | Description |
| :--- | :--- | :--- |
| R | [0.0, 0.0, 0.0] | Angle parameters; the first group is 0.0 pitch angle, the second group is 0.0 heading angle, and the third group is 0.0 roll angle. |
| t | [0.0, 0.0, 0.0] | Offset parameters; the first group is 0.0 lateral offset parameter, the second group is 0.0 (not effective), and the third group is 0.0 depth offset (forklift front and rear direction). |
| two_leg | 0 | Whether to enable two legs; if there is no two-legged pallet in the application, it is not recommended to enable it. 0 is closed, 1 is open. |
| ground_y | 331 | Installation height in MM. |
| min_leg | 30 | Minimum leg width supported. |
| max_leg | 170 | Maximum leg width supported. |
| thickness | 15 | Algorithm extraction thickness. |
| x-client | "nonetest" | Customer name (and forklift serial number) for future maintenance. |
| orientation | 0 | Installation method; 0 is upright, 2 is inverted; 1, 3 are side-mounted. |
| min_z | 1000 | Minimum range for recognition; it does not recognize within 1000. |
| max_z | 3200 | Maximum range for recognition; it does not recognize beyond 3200. |
| min_x | -980 | Horizontal direction filtering; not recognized beyond 980mm to the left of the center. |
| max_x | 980 | Horizontal direction filtering; not recognized beyond 980mm to the right of the center. |

## Menu bar
The four options—External Calibration, Camera Operations, Advanced Parameters, and Save Parameters—are also included in Basic Operations and Advanced Applications. The following sections will only describe the parameters within Basic Operations and Advanced Applications.


<p align="center">
<img alt="PixPin_2026-06-09_12-20-32" src="https://github.com/user-attachments/assets/78b106bc-2d67-45bc-9d11-32ce54cee9d5" />
<br>
  <em>Figure 3: Menu bar</em>
</p>

### Basic Operations

| Menu | Option | Description |
| :--- | :--- | :--- |
| Basic Operations | Extrinsic Calibration | Camera calibration, including camera height, lateral offset, pitch angle, yaw angle, and roll angle. |
| Basic Operations | Save Parameters | Save the configured parameters and send them to the camera. |
| Camera Operations | Get Camera Info | Retrieve the camera IP, camera ID, and software logs. |

#### External Calibration Module
Click External Calibration under Basic Operations. The extrinsic calibration interface will be displayed on the right side of the software window.

<p align="center">
<img  alt="PixPin_2026-06-09_12-21-07" src="https://github.com/user-attachments/assets/f323033b-31cc-4bcc-8650-5b58a19739b9" />
<br>
  <em>Figure 4 : External calibration module</em>
</p>

Click 'External Calibration' and then select 'Calibration Notes' to display the precautions for external calibration. Please read them carefully to avoid any issues during the process.
<p align="center"><img width="415" height="468" alt="PixPin_2026-06-09_12-21-48" src="https://github.com/user-attachments/assets/2208e4e5-6f5b-4ad3-bb63-99020e040bbc" />
<br>
  <em>Figure 5 : External calibration notes</em>
</p>

# 4. Initial setup and Calibration going through
Install LxCameraViewer and PalletPro software on a Windows operating system, 
set up and prepare the software before testing.

## 3.1 Camera installation
As shown in the figure below, it is advisable to mount the camera at a height of around 400mm.
Position the pallet directly in front of the camera at a distance of 1500mm.
Note: Ensure that the front surface of the camera is positioned close to the edge of the object 
supporting the camera to prevent any blockage of emitted or reflected infrared light.



## 3.2 Camera configuration (MRDVS)

1. Before connecting the camera, please complete the following setup:

- The factory default IP address of the camera is 192.168.100.82. Ensure that your local network port (or Ethernet adapter) is configured to be in the same subnet before establishing a connection.

- Disable the firewall.

- For more details about IP and Firewall configuration, please see the LxCameraViewer use manual at https://github.com/Lanxin-MRDVS/CameraSDK/wiki/LxCameraViewer-User-Manual


<p align="center">
<img width="50%" height="50%"  alt="Näyttökuva 2026-06-08 kello 9 44 01" src="https://github.com/user-attachments/assets/c553a115-6aea-4da1-b6c9-658bb249b346" />
<br>
  <em>Figure 2: IP configuration</em>
</p>

2. Open the LxCameraViewer to test the camera view. Glick the [3D settings] tab. The default camera high exposure value is 650, and the low exposure value is 200. Adjust the camera exposure value based on different application scenarios.

<p align="center">
<img width="50%" height="50%" alt="PixPin_2026-06-08_04-36-24" src="https://github.com/user-attachments/assets/325269dc-cad8-4ae0-bf5a-93cabe51c628" />
<br>
  <em>Figure 3: Camera configuration</em>
</p>

4. Select the pallet positioning algorithm and set the working mode to Close on Disconnect.
Note: LxCameraviewer is only used for configuring camera internal parameters, while PalletPro handles all other algorithm parameters. For better recognition performance, we recommend upgrading to the latest version of PalletPro via a firmware update

<p align="center">
<img  width="50%" height="50%" alt="PixPin_2026-06-08_05-46-26" src="https://github.com/user-attachments/assets/ee38fd74-d705-4851-9343-9e1887bc9083" />
<br>
  <em>Figure 4: Camera configuration</em>
</p>

## 3.3 Pallet algorithm configuration (PalletPro)

1. Before opening PalletPro, exit LxCameraViewer first. Then open the Pallet Recognition software PalletPro.

2. After opening PalletPro, it will automatically scan the camera. Click on the [start camera] tab to open and obtain the camera data stream.

<p align="center">
<img  alt="PixPin_2026-06-09_12-42-49" src="https://github.com/user-attachments/assets/ac3e174f-a146-4b43-bb37-97d501ae3672" />
<br>
  <em>Figure 5: Start Camera</em>
</p>
   


3. Click on [parameter settings] tab, which shows the current position of the camera. If the parameters are all default 0 while connecting the PalletPro to the camera first time, click the adaptive button to get the approximate installation height of the current camera. Then fine-tune it, as shown in the diagram, adjusting the auxiliary line value to the intersection position of the pallet and the ground. Click save parameters, check [real-time display], and [real-time detection] to achieve pallet recognition display functionality.


## 3.4 Pallet calibration preparation

1. Preparation:
   - A standard European blue plastic pallet, 1200mm×1200mm×150mm, as shown in the diagram.
   - A tape measure.
   - A forklift that can move normally
  
Note: The ground should be relatively flat during calibration. Before calibration, refer to the simple test method mentioned in 3.1 to set the approximate installation height of the camera. Then, when the forklift moves back and forth, both the far-end calibration and the near-end calibration can recognize the pallet stably.
  
     
## 3.5 Near-end calibration 

The near-end calibration scheme uses a so called teaching calibration method. The forklift needs to manually control the docking of the pallet once. First, move the forklift under the pallet, and pick up the pallet once, which makes sure that the forklift is centered in terms of the pallet. Then, lift down the lift arm, and in a straight line, drive the forklift (the pallet is on the ground without lifting) to make the fork tip about 200mm away from the front edge of the pallet (as shown in the diagram). At this time, click on the [pallet teaching (near)] to calibrate the installation height, lateral offset, heading angle, and roll angle. After calibration, click [Real-time display] and [Detection] to continue detection. 

## 3.6 Far-end calibration
The far-end calibration function is to calibrate the pitch angle of the camera installation. After completing the near-end calibration, ensure that the pallet position remains unchanged, control the forklift to move away from the pallet, and click on the [pallet teaching (far)] when the distance displayed on PalletPro is in the range of 2300mm-2500mm. This will calibrate the pitch angle of the camera installation. Click save parameters to complete the calibration. As shown in the diagram.


## 3.7 Calibration verification

Once the near-end and far-end calibrations are complete, you can begin verifying the calibration accuracy. Move the forklift back and forth between the near-end and far-end calibration points while monitoring the R output for distance (X value), lateral deviation (Y value), and angle. Calibration is considered successful when the X and Y errors are within 10 mm and the recognition is stable with no missed detections. The forklift can then be put into normal operation.


