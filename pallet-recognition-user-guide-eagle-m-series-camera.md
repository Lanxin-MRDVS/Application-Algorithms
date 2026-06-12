# Pallet Recognition User Guide - Eagle-M Series Camera

## 1. Introduction

Pallet recognition is a solution developed by MRDVS using the in-house developed Eagle-M series cameras. It's is designed for forklifts to seamlessly docking pallets. The system boasts adaptive compatibility with a range of pallet specifications, eliminating the need for specific configurations. With dynamic detection capabilities, it can identify structures on the go, eliminating the requirement for the vehicle to come to a complete stop. The system is versatile, supporting recognition in diverse scenarios like floor-to-floor transitions, storage locations, and shelves. Adaptive Pallet Recognition, The system can adaptively recognize pallets of different specifications, including wooden and plastic pallets with different shapes, as shown below.

<p align="center"><img src="https://github.com/user-attachments/assets/07ea19b2-275a-4697-bbbe-932926c33afc" alt="Picture3"><br></p>

<p align="center"><img src="https://github.com/user-attachments/assets/b9e6997f-2853-4967-94bb-2f980dbd7ac4" alt="Picture2"><br></p>

<p align="center"><img src="https://github.com/user-attachments/assets/4e9ed2c6-5b31-4dd9-8c6d-b36cdfb230d8" alt="Picture5"><br></p>

<p align="center"><img src="https://github.com/user-attachments/assets/7c750174-1cc7-45d8-b5ab-2b93efc2f910" alt="Picture4"><br></p>

## 2. Eagle-M camera installation

As shown in the figure below, install the Eagle-M camera at a distance of 35cm to 45cm above the base panel of the fork arm, ensuring it is close to the center of the two fork teeth (with a left-right deviation of no more than 5cm).

<p align="center">
  
<img length="50%" width="50%" alt="Näyttökuva 2026-06-08 kello 11 00 12" src="https://github.com/user-attachments/assets/f77877a6-e6b3-45df-9e1e-355a2744c463" />
<br><em>Figure 1: Installation example</em></p>

## 3. Interfaces

### 3.1 Main Interface

After launching the software, the main interface shown below will appear. You can perform operations such as camera connection, camera calibration, and pallet recognition on this screen.

<p align="center"><img src="https://github.com/user-attachments/assets/d70a5468-f972-4d3c-86bd-e2aac69758ca" alt="PixPin_2026-06-09_12-18-31"><br><em>Figure 2: Main Interface</em></p>

The interface includes the following functions:

| Function Module           | Specific Functions/Description                                                                                                       |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| Menu Bar                  | Includes basic operations, advanced applications, extrinsic calibration, camera operations, advanced parameters, and save parameters |
| Camera Parameter Settings | Includes scanning, embedded mode, camera on/off, real-time display, detection, projection, and camera calibration parameter settings |
| File Import               | Includes calibration parameter files, recognition images, and folders                                                                |
| Log Printing              | Prints detection results, camera firmware version, algorithm version, etc.                                                           |
| Image Display             | Displays image dat                                                                                                                   |

### 3.2 Menu bar

The five options—External Calibration, Camera Operations, Advanced Parameters, Save Parameters, and Languages—are also included in Basic Operations and Advanced Applications.

<p align="center"><img src="https://github.com/user-attachments/assets/78b106bc-2d67-45bc-9d11-32ce54cee9d5" alt="PixPin_2026-06-09_12-20-32"><br><em>Figure 3: Menu bar</em></p>

### 3.3 Basic Operations

| Menu              | Option                | Description                                                                                          |
| ----------------- | --------------------- | ---------------------------------------------------------------------------------------------------- |
| Basic Operations  | Extrinsic Calibration | Camera calibration, including camera height, lateral offset, pitch angle, yaw angle, and roll angle. |
| Basic Operations  | Save Parameters       | Save the configured parameters and send them to the camera.                                          |
| Basic Operations | Camera Operations      | Retrieve the camera IP, camera ID, and software logs.                                                |

#### 3.3.1 External Calibration Module

Click External Calibration under Basic Operations. The extrinsic calibration interface will be displayed on the right side of the software window.

<p align="center"><img src="https://github.com/user-attachments/assets/f323033b-31cc-4bcc-8650-5b58a19739b9" alt="PixPin_2026-06-09_12-21-07"><br><em>Figure 4: External calibration module</em></p>

Click 'External Calibration' and then select 'Calibration Notes' to display the precautions for external calibration. Please read them carefully to avoid any issues during the process.

<p align="center">
<img alt="PixPin_2026-06-09_12-21-48" src="https://github.com/user-attachments/assets/58904c8f-b0ed-4f78-b862-d80fd9542096" />
<br><em>Figure 5: External calibration notes</em></p>

Information verification at the Bottom of [Calibration Notes]: Customer Name: It is recommended to use the format "Project Name + Forklift Number" for easier troubleshooting as shown in Figure 6. Minimum Recognition Distance (mm): Keep the default value as shown in Figure 6. (If the calibration distance is relatively short, adjust it to 1.2m.)

<p align="center">
<img alt="PixPin_2026-06-10_11-20-50" src="https://github.com/user-attachments/assets/8672da0b-1ff7-4ed6-98ca-5b59104f8923" />
<br><em>Figure 6 : Information verification</em></p>


Distance from Rotation Center to Optical Center: When set to the default value of 0, it represents the coordinate of camera's optical center is overlapping with the forklift's rotation center. You must enter the actual distance from the camera's optical center to the forklift's rotation center.
Fork Arm Position (Depth to Tray Edge): This parameter defines the additional insertion distance the forklift arm needs to travel after reaching the front edge of the pallet. It acts as a safety margin to ensure the forks are fully and securely inserted under the pallet.

<p align="center">
<img alt="PixPin_2026-06-10_11-31-24" src="https://github.com/user-attachments/assets/cd0cc029-04f3-4801-a8c8-42fc44a7e9b8" />
<br><em>Figure 7: Parameters</em></p>


Pallet Teaching (It is recommended to perform two calibrations): \[Pallet Teaching (Near)]: Position the pallet 200mm away from the forklift forks to perform near-end calibration. This step determines the pallet's height, lateral offset, heading angle, and roll angle. \[Pallet Teaching (Far)]: After near-end calibration, proceed with far-end calibration (secondary teaching). For example, if the camera recognizes the pallet distance as 1300mm during near-end calibration, drive the forklift straight backward by approximately 400–800mm without any angular or lateral movement. Perform far-end calibration when the distance to the pallet reaches 1.8–2.4m. This step determines the camera's pitch angle. Note: \[Pallet Teaching (Far)] tab is only available after \[Pallet Teaching (Near)] is successful.

<p align="center">
<img alt="PixPin_2026-06-10_11-31-24" src="https://github.com/user-attachments/assets/eadf1f1c-7927-4a4f-bcd9-3a4572537e45" />
<br><em>Figure 8: Pallet Teaching</em></p>



Clicking 'Reset Calibration' will restore all external calibration parameters to zero.

<p align="center">
<img  alt="PixPin_2026-06-10_11-10-32" src="https://github.com/user-attachments/assets/17bce3f3-1a9f-4c17-b76d-a716e2a982dd" />
<br><em>Figure 9: Reset Calibration</em></p>

Lateral deviation means the literal deviation between the camera's optical center and forklift's coordinate center, and it is automatically determined through the calibration process.



Note: Method 2 is a custom feature for other client, you can dismiss that.

#### 3.3.2 Camera Operations

The [Camera Operations] section displays the camera's internal parameters.

<p align="center">
<img alt="PixPin_2026-06-11_10-17-01" src="https://github.com/user-attachments/assets/ac58f77e-8e79-4be4-a964-437275a58079" />
<br><em>Figure 10: Camera Operations</em></p>



[Camera IP]: Displays the IP address of the connected camera.

[Camera ID]: Displays the ID of the connected camera.

[Get lanxin vision log]: Click this button to save the camera detection log to the platform folder as file lanxin_vision_log.

[Camera docking system Configuration]: This section is for administrators only to configure the docking system. Do not modify these settings.


<p align="center">
<img alt="PixPin_2026-06-11_10-32-07" src="https://github.com/user-attachments/assets/a71bdc4d-1a84-4f7d-b182-1cb3bba83f04" />
<br><em>Figure 11: Camera docking system Configuration </em></p>

[Advanced Parameters Configuration]: By clicking [Pull], the current advanced parameters will be loaded into the platform folder as /docking_config.json. Next, click [Configure the algorithm parameters] to show and adjust the parameters within the platform, and finally click [Upload].

<p align="center">
<img  alt="PixPin_2026-06-11_10-33-41" src="https://github.com/user-attachments/assets/1db72dff-ae36-44af-bc77-41c57164e152" />
<br><em>Figure 12: Advanced Parameters Configuration</em></p>



### 3.4 Advanced applications Interface

#### 3.4.1 Advanced parameters 

Camera configuration file: The camera configuration file "pallet\_settings.json", which contains the camera algorithm parameters, will be downloaded and loaded into PalletPro.

Camera IP/ID: Displays the IP address and ID of the connected camera.

Leg width: The width of the legs on the side facing the camera.

Pallet width: The width of the pallet on the side facing the camera.

Crossbar width: The width of the pallet crossbar on the side facing the camera.

| Setting                      | Mode Option        | Parameter / Description           |
| ---------------------------- | ------------------ | --------------------------------- |
| **Leg Width Selection**      | Standard Mode      | 10-15cm                           |
|                              | Thin Fork Mode     | 5cm                               |
|                              | Ultra-thin Pallet  | 3-4cm                             |
|                              | Wider              | 15cm                              |
|                              | Extra Wide         | 20cm+                             |
|                              | 8 - 32 cm          | 8-32cm                            |
|                              | Custom number      | Custom number                     |
| **Pallet Width Selection**   | Standard Mode      | 0.7-1.3m                          |
|                              | Wide Pallet        | 1.1-1.6m                          |
|                              | Custom number      | Custom number                     |
| **Crossbar Width Selection** | Standard (Default) | No changes needed for general use |
|                              | Thinner            | 80%                               |
|                              | Very Thin          | 60%                               |
|                              | Sparse             | 10%                               |


<p align="center">
<img  alt="PixPin_2026-06-11_05-13-00" src="https://github.com/user-attachments/assets/bd6adef2-26da-43b7-9450-1ba390c8a584" />
<br><em>Figure 13: Advanced parameters 1</em></p>

**Camera algorithm parameters which can be modified in advanced settings:**

| Parameter   | Value/Status     | Description                                                                                                                                                                               |
| ----------- | ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| R           | \[0.0, 0.0, 0.0] | Angle parameters; the first group is 0.0 pitch angle, the second group is 0.0 heading angle, and the third group is 0.0 roll angle.                                                       |
| t           | \[0.0, 0.0, 0.0] | Offset parameters; the first group is 0.0 lateral offset parameter, the second group is 0.0 (not effective), and the third group is 0.0 depth offset (forklift front and rear direction). |
| two\_leg    | 0                | Whether to enable two legs; if there is no two-legged pallet in the application, it is not recommended to enable it. 0 is closed, 1 is open.                                              |
| ground\_y   | 331              | Installation height in mm.                                                                                                                                                                |
| min\_leg    | 30               | Minimum leg width supported.                                                                                                                                                              |
| max\_leg    | 170              | Maximum leg width supported.                                                                                                                                                              |
| thickness   | 15               | Algorithm extraction thickness.                                                                                                                                                           |
| x-client    | "nonetest"       | Customer name (and forklift serial number) for future maintenance.                                                                                                                        |
| orientation | 0                | Installation method; 0 is upright, 2 is inverted; 1, 3 are side-mounted.                                                                                                                  |
| min\_z      | 1000             | Minimum range for recognition; it does not recognize within 1000.                                                                                                                         |
| max\_z      | 3200             | Maximum range for recognition; it does not recognize beyond 3200.                                                                                                                         |
| min\_x      | -980             | Horizontal direction filtering; not recognized beyond 980mm to the left of the center.                                                                                                    |
| max\_x      | 980              | Horizontal direction filtering; not recognized beyond 980mm to the right of the center.                                                                                                   |

Expanded Parameters: Expansion of existing parameters, but modification is not recommended.

<p align="center">
<img alt="PixPin_2026-06-11_05-13-20" src="https://github.com/user-attachments/assets/144d5cf2-489e-4231-862a-9942d83cd89a" />
<br><em>Figure 14: Advanced parameters 2</em></p>

#### 3.4.2 Display 3D

Select 'Advanced Application' and click the [Display 3D] tab to display the current 3D point cloud. You can adjust the page dimensions by dragging its edges，hold down the left mouse button and use the scroll wheel to zoom in or out，or hold down the left mouse button and drag to rotate or tumble the image. This feature can also be used during offline testing to check the completeness of the pallet point cloud.

<p align="center"><img alt="PixPin_2026-06-11_10-16-21" src="https://github.com/user-attachments/assets/8caba97f-0406-48a8-b7c5-337e5e8f94e6" />
<br><em>Figure 15: Display 3D image</em></p>

#### 3.4.3 Offline Testing Module

Select [Advanced Application] and click the [Offline Testing] tab. To recognize offline images, import a JSON calibration calibration parameter file, a single image or an image folder into PalletPro, choose [File] or [Folder] option, and then click the [Start Detection] button. 
<p align="center">
<img alt="PixPin_2026-06-10_10-26-32" src="https://github.com/user-attachments/assets/8f49a205-95c9-4992-bd90-370ef1581f00" />
<br><em>Figure 16: Offline testing module</em></p>

Normally, a JSON parameter file is automatically generated into the PalletPro application folder upon connecting to the camera. However, if you wish to test the PalletPro algorithm offline, you can create your own JSON parameter file following the format as shown below. Place this file in the root directory of the application, and specify its path in the [Parameter file] field as shown in Figure 4.

```json
{
  "R": {
    "key": "R",
    "value": [0.0, 0.0, 0.0],
    "level": 1,
    "desc": "euler angles"
  },
  "t": {
    "key": "t",
    "value": [0.0, 0.0, 0.0],
    "level": 1,
    "desc": "translation vector"
  },
  "ground_y": {
    "key": "ground_y",
    "value": -100,
    "level": 1,
    "desc": "地面高度，单位毫米"
  },
  "fork_space": {
    "key": "fork_space",
    "value": 20,
    "level": 1,
    "desc": "相机与叉臂间隙"
  },
  "thickness": {
    "key": "thickness",
    "value": 15,
    "level": 1,
    "desc": "算法提取厚度"
  },
  "multi_level": {
    "key": "multi_level",
    "value": 0,
    "level": 1,
    "desc": "是否支持多托盘检测"
  },
  "x-client": {<img width="1920" height="1028" alt="PixPin_2026-06-11_10-16-21" src="https://github.com/user-attachments/assets/a106cf48-e605-4b71-a50f-536fd9806d42" />

    "key": "x-client",
    "value": "none",
    "level": 1,
    "desc": "客户名称"
  },
  "fork_angle": {
    "key": "fork_angle",
    "value": 0,
    "level": 1,
    "desc": "叉臂与叉车直线运动方向的夹角，一般为0"
  },
  "two_leg": {
    "key": "two_leg",
    "value": 0,
    "level": 1,
    "desc": "是否支持双腿"
  },
  "fork_insert": {
    "key": "fork_insert",
    "value": 0,
    "level": 1,
    "desc": "叉车旋转中心到托盘前沿后，需要继续插入的距离"
  },
  "orientation": {
    "key": "orientation",
    "value": 0,
    "level": 1,
    "desc": "安装方式；0为正装，2为倒装；1、3侧装"
  },
  "min_z": {
    "key": "min_z",
    "value": 800,
    "level": 1,
    "desc": "z方向最小值"
  },
  "max_z": {
    "key": "max_z",
    "value": 3200,
    "level": 1,
    "desc": "z方向最大值"
  },
  "min_x": {
    "key": "min_x",
    "value": -980,
    "level": 1,
    "desc": "水平方向最小值"
  },
  "max_x": {
    "key": "max_x",
    "value": 980,
    "level": 1,
    "desc": "水平方向最大值"
  },
  "quad": {
    "key": "quad",
    "value": 0,
    "level": 2,
    "desc": "是否支持四腿托盘"
  },
  "scan_step": {
    "key": "scan_step",
    "value": 1,
    "level": 2,
    "desc": ""
  },
  "min_line_count": {
    "key": "min_line_count",
    "value": 60,
    "level": 2,
    "desc": ""
  },
  "log_level": {
    "key": "log_level",
    "value": 0,
    "level": 2,
    "desc": ""
  },
  "cutting_height": {
    "key": "cutting_height",
    "value": 50,
    "level": 2,
    "desc": ""
  },
  "space_dist": {
    "key": "space_dist",
    "value": 25,
    "level": 2,
    "desc": ""
  },
  "max_legwidth_diff": {
    "key": "max_legwidth_diff",
    "value": 50,
    "level": 2,
    "desc": "左右腿最大差异"
  },
  "min_hole": {
    "key": "min_hole",
    "value": 280,
    "level": 2,
    "desc": ""
  },
  "max_hole": {
    "key": "max_hole",
    "value": 700,
    "level": 2,
    "desc": ""
  },
  "leg_dist_min": {
    "key": "leg_dist_min",
    "value": 500,
    "level": 2,
    "desc": "<双腿检测>左右腿最小距离"
  },
  "leg_dist_max": {
    "key": "leg_dist_max",
    "value": 1600,
    "level": 2,
    "desc": "<双腿检测>左右腿最大距离"
  },
  "denoise_search_radius": {
    "key": "denoise_search_radius",
    "value": 25,
    "level": 2,
    "desc": ""
  },
  "denoise_min_pts": {
    "key": "denoise_min_pts",
    "value": 20,
    "level": 2,
    "desc": ""
  },
  "bar_check_dist": {
    "key": "bar_check_dist",
    "value": 100,
    "level": 2,
    "desc": ""
  },
  "bar_search_y": {
    "key": "bar_search_y",
    "value": 12,
    "level": 2,
    "desc": ""
  },
  "max_hole_diff": {
    "key": "max_hole_diff",
    "value": 91,
    "level": 2,
    "desc": "最大托盘孔距差异"
  }
}
```

<p align="center">
<img alt="PixPin_2026-06-10_10-11-14" src="https://github.com/user-attachments/assets/c8a94deb-81fa-4902-9ea8-fa9b71bee415" />
<br><em>Figure 17: Offline testing module</em></p>


Then add the target pointcloud image to the PalletPro folder and specify its path in the [Input file] section. Then, click [Start Detection]. 

<p align="center">
<img alt="PixPin_2026-06-10_10-38-43" src="https://github.com/user-attachments/assets/b79e3b84-c45a-40a6-8db1-4b71f126836f" />
<br><em>Figure 18: Add offline pointcloud image</em></p>

Or you can also specify the path of the folder containing the images in the [Folder] section, enter the order of the picture from which you want to test, and then, click [Start Detection], and the Algorithm will automatically find the picture inside the folder. 


<p align="center">
<img  alt="PixPin_2026-06-10_10-20-47" src="https://github.com/user-attachments/assets/529560da-785b-47fc-9022-4791ea1db1bd" />
<br><em>Figure 19: Add offline pointcloud image folder</em></p>

**Example:**
<p align="center"><img alt="PixPin_2026-06-10_10-20-20" src="https://github.com/user-attachments/assets/b5cc3e33-e553-4742-a8d0-130d21c039aa" />
<br><em>Figure 20: Example format</em></p>

Note: The offline testing module will automatically perform the detection, so you don't need to do [Pallet Teaching (far)] and [Pallet Teaching (near)] separately if the forklift's moving range is within 2000 mm of the pallet.

## 4. Initial setup and Calibration going through

Install LxCameraViewer and PalletPro software on a Windows operating system, set up and prepare the software before testing.

### 4.1 Camera installation

As shown in the figure below, it is advisable to mount the camera at a height of around 400mm. Position the pallet directly in front of the camera at a distance of 1500mm. Note: Ensure that the front surface of the camera is positioned close to the edge of the object supporting the camera to prevent any blockage of emitted or reflected infrared light.

<p align="center">
<img alt="Picture6" src="https://github.com/user-attachments/assets/3d8ee678-2126-49df-8054-f8dc29d96853" />
<br><em>Figure 21: Camera installation example </em></p>


### 4.2 Camera configuration (MRDVS)

1. Before connecting the camera, please complete the following setup:

* The factory default IP address of the camera is 192.168.100.82. Ensure that your local network port (or Ethernet adapter) is configured to be in the same subnet before establishing a connection.
* Disable the firewall.
* For more details about IP and Firewall configuration, please see the LxCameraViewer use manual at https://github.com/Lanxin-MRDVS/CameraSDK/wiki/LxCameraViewer-User-Manual

<p align="center">
<img alt="Picture1" src="https://github.com/user-attachments/assets/1a1a0010-12b5-4972-a9bd-e084c3d91a51" />
<br><em>Figure 22: IP configuration</em></p>

2. Open the LxCameraViewer to test the camera view. Glick the [3D settings] tab. The default camera high exposure value is 650, and the low exposure value is 200. Adjust the camera exposure value based on different application scenarios.

<p align="center">
<img  alt="PixPin_2026-06-11_07-52-05" src="https://github.com/user-attachments/assets/e3168c7b-6aa6-4b07-94fe-5b12bf31fbba" />
<br><em>Figure 23: Camera configuration</em></p>

4. Select the pallet positioning algorithm and set the working mode to [Keep Heartbeat]. Note: LxCameraviewer is only used for configuring camera internal parameters, while PalletPro handles all other algorithm parameters. For better recognition performance, we recommend upgrading to the latest version of PalletPro via a firmware update.

<p align="center">
<img alt="PixPin_2026-06-11_07-56-54" src="https://github.com/user-attachments/assets/5dd64e77-5fb7-4e64-96e0-7390397f9737" />
<br><em>Figure 24: Camera configuration</em></p>

### 4.3 Pallet algorithm configuration (PalletPro)

1. Before opening PalletPro, exit LxCameraViewer first. Then open the Pallet Recognition software PalletPro.
2. After opening PalletPro, it will automatically scan the camera. Click on the \[start camera] tab to open and obtain the camera data stream.

<p align="center"><img src="https://github.com/user-attachments/assets/ac3e174f-a146-4b43-bb37-97d501ae3672" alt="PixPin_2026-06-09_12-42-49"><br><em>Figure 5: Start Camera</em></p>

3. Click on [parameter settings] tab, which shows the current position of the camera. If the parameters are all default 0 while connecting the PalletPro to the camera first time, click the [auto-adjusting high] button to get the approximate installation height of the current camera. Then fine-tune it, as shown in the diagram, adjusting the auxiliary line value to the intersection position of the pallet and the ground. Click save parameters, check [real-time display], and [real-time detection] to achieve pallet recognition display functionality.

<p align="center">
<img alt="PixPin_2026-06-11_08-16-15" src="https://github.com/user-attachments/assets/71fe6cb5-6d7c-4cbb-b21d-1bf18f8511aa" />
<br><em>Figure 25: Parameter Settings</em></p>

### 4.4 Pallet calibration preparation

1. Preparation:
   * A standard European blue plastic pallet, 1200mm×1200mm×150mm, as shown in the diagram.
   * A tape measure.
   * A forklift that can move normally

Note: The ground should be relatively flat during calibration. Before calibration, refer to the simple test method mentioned in 3.1 to set the approximate installation height of the camera. Then, when the forklift moves back and forth, both the far-end calibration and the near-end calibration can recognize the pallet stably.

<p align="center"><img src="https://github.com/user-attachments/assets/2a84a161-f9aa-4f71-85ed-cc51699df9e3" alt="图片2"><br><em>Figure 26: Pallet</em></p>

### 4.5 Near-end calibration

The near-end calibration scheme uses a so called teaching calibration method. The forklift needs to manually control the docking of the pallet once. First, move the forklift under the pallet, and pick up the pallet once, which makes sure that the forklift is centered in terms of the pallet. Then, lift down the lift arm, and in a straight line, drive the forklift (the pallet is on the ground without lifting) to make the camera about 1300mm away from the front edge of the pallet (as shown in the diagram). At this time, click on the [pallet teaching (near)] to calibrate the installation height, lateral offset, heading angle, and roll angle. After calibration, click [Real-time display] and [Detection] to continue detection.

<p align="center"><img src="https://github.com/user-attachments/assets/405aa2cd-0040-4078-a1ad-b54f6f09fa04" alt="图片3"><br><em>Figure 27: Pickup first</em></p>

<p align="center"><img src="https://github.com/user-attachments/assets/c5afa644-e76b-4d79-ae6d-ea3e211cd014" alt="图片4"><br><em>Figure 28: Lift down and move backward</em></p>

<p align="center">
<img alt="PixPin_2026-06-11_08-27-53" src="https://github.com/user-attachments/assets/6b962439-78e8-4be6-83ba-049a1c86075c" />
<em>Figure 29: Lift down and move backward</em></p>



### 4.6 Far-end calibration

The far-end calibration function is to calibrate the pitch angle of the camera installation. After completing the near-end calibration, ensure that the pallet position remains unchanged, control the forklift to move away from the pallet, and click on the [pallet teaching (far)] when the distance displayed on PalletPro is in the range of 2000mm-2400mm. This will calibrate the pitch angle of the camera installation. Click save parameters to complete the calibration. As shown in the diagram.

Note: The [Pallet Teaching (far)] is not mandatory, if the forklift's moving range is within 2000 mm of the pallet.

<p align="center">
<img alt="Picture7" src="https://github.com/user-attachments/assets/16605e1f-868b-40f1-b0c2-039135965f06" />
<br><em>Figure 30: Distance 2000mm - 2400mm</em></p>

<p align="center">
<img alt="PixPin_2026-06-11_08-36-59" src="https://github.com/user-attachments/assets/f021bd37-7b8d-44b3-b031-939c86794d87" />
<br><em>Figure 31: Distance 2000mm - 2400mm</em></p>

### 4.7 Calibration verification

Once the near-end and far-end calibrations are complete, you can begin verifying the calibration accuracy. Move the forklift back and forth between the near-end and far-end calibration points while monitoring the R output for distance (X value), lateral deviation (Y value), and angle. Calibration is considered successful when the X and Y errors are within 10 mm and the recognition is stable with no missed detections. The forklift can then be put into normal operation.

Example: x, y, theta = (-1987, 81, -2.1)
This signifies that the pallet is 1987 millimeters away from the camera's optical center, shifted right by 81 millimeters, with an angular deviation of -2.3° (top view, counterclockwise direction).
The data result is X: -1987; Y: 81; Theta: -2100.

<p align="center">
<img alt="PixPin_2026-06-11_08-39-02" src="https://github.com/user-attachments/assets/f2c5d344-a009-4461-8671-041f0132e574" />
<br><em>Figure 32: Verification</em></p>

## 5. Data communication methods 

Here, we used NetAssist as the communication configuration tool for TCP and UDP. You can download it from https://www.cmsoft.cn/resource/102.html, as shown in Figure 33. 

You can also use NetAssistant from https://github.com/luokyme/NetAssistant, which includes English documentation, but it has not been tested with this instruction.


<p align="center">
<img width="50%" height="50%" alt="Näyttökuva 2026-06-02 kello 9 42 36" src="https://github.com/user-attachments/assets/c65c8633-d35c-4e83-b12c-712988e689ae" />
<br>
  <em>Figure 33: Download site </em>
</p>

### 5.1 API Invocation

The API invocation method supports C++, C#, JAVA, ROS1, ROS2, and other environments on Windows, Linux, ARM, etc. For the Windows environment, after installing the upper computer software, SDK files, and sample program codes are available in the installation path (e.g., D:\Program Files\Lanxin-MRDVS). 
- Document Folder: Contains SDK and upper computer usage documentation.
- Firmware Folder: Stores camera firmware packages.
- Sample Folder: Holds sample code source files for various development environments.
- SDK Folder: Contains SDK library files, and environment variables can be configured according to the development environment.


### 5.2 UDP Communication 

Set the algorithm working mode to open on the NetAssist.

**Port Configuration:**
Host Port Number: 8000

**Sending Content:**
1.0x60 0x04 0x00 0x00 means Start Recognition Task
2.0x60 0x04 0x00 0x01 means End Recognition Task

Character explanation: 00 00 00 14 01 00 00 00 00 17 8E 78 00 00 17 70 00 00 28 F5 00

### Response Data Structure

| Byte Position | Content | Description |
| :--- | :--- | :--- |
| **1-2** | Code | Returns a 16-bit unsigned integer (`unsigned int`).<br>• `0`: Success<br>• `1`: Camera open exception<br>• `2`: Pallet positioning failure<br>• `3`: Internal camera exception |
| **3-4** | Total Byte Length | 16-bit unsigned integer (`unsigned int`). Current value is **20 bytes**. |
| **5-8** | Pallet Recognition (X, Y, Theta) | The sign is represented by `0x00` for positive and `0x01` for negative. The 8th byte is a placeholder (`0x00`). |
| **9-12** | Pallet Front Center X Position | 4-byte unsigned integer. Unit: **millimeters (mm)**. |
| **13-16** | Pallet Front Center Y Position | 4-byte unsigned integer. Unit: **millimeters (mm)**. |
| **17-20** | Pallet Front Center Angle Theta | 4-byte unsigned integer. Unit: **degrees × 1000**. |

### 5.3 TCP Communication


### 5.5 CAN Communication
Please note the Can protocol only supports M4 cameras.
The communication protocol adopts CANopen. The CANopen protocol is an application layer protocol running on the standard CAN bus. Its communication mode is the commonly used "master-slave" mode in industrial communication protocols. In this mode, there is one master station + multiple slave stations, and slave stations do not communicate directly with each other. All communication is between the master station and slave stations. The master station is also referred to as the "client," and the slave station is referred to as the "server." 
The underlying communication method uses the CAN standard frame format, where the CAN ID is 11 bits (0x000~7FF), and the data is 8 bytes.
For the use of CAN IDs:
Divide the 11-bit ID into a 4-bit function code and a 7-bit node ID. The CAN ID is also called COB ID.
