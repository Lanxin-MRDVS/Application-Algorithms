# 1. Introduction 

Pallet recognition is a solution developed by MRDVS using the in-house developed Eagle-M series cameras. 
It's is designed for forklifts to seamlessly docking pallets. 
The system boasts adaptive compatibility with a range of pallet specifications, 
eliminating the need for specific configurations. With dynamic detection capabilities,
it can identify structures on the go, eliminating the requirement for the vehicle to come to a complete stop.
The system is versatile, supporting recognition in diverse scenarios like floor-to-floor transitions, storage locations, and shelves.
Adaptive Pallet Recognition, The system can adaptively recognize pallets of different specifications, 
including wooden and plastic pallets with different shapes, as shown below.


# 2. Eagle-M camera installation

As shown in the figure below, install the Eagle-M camera at a distance of 35cm to 45cm above the base panel 
of the fork arm, ensuring it is close to the center of the two fork teeth (with a left-right deviation of 
no more than 5cm).


# 3. Initial setup and Calibration
Install LxCameraViewer and PalletPro software on a Windows operating system, 
set up and prepare the software before testing.

## 3.1 Camera installation
As shown in the figure below, it is advisable to mount the camera at a height of around 400mm.
Position the pallet directly in front of the camera at a distance of 1500mm.
Note: Ensure that the front surface of the camera is positioned close to the edge of the object 
supporting the camera to prevent any blockage of emitted or reflected infrared light.



## 3.2 Camera connection (MRDVS)

1. Before connecting the camera, please complete the following setup:

- The factory default IP address of the camera is 192.168.100.82. Ensure that your local network port (or Ethernet adapter) is configured to be in the same subnet before establishing a connection.

- Disable the firewall.

- For more details about IP and Firewall configuration, please see the LxCameraViewer use manual at https://github.com/Lanxin-MRDVS/CameraSDK/wiki/LxCameraViewer-User-Manual


<p align="center">
<img width="50%" height="50%"  alt="Näyttökuva 2026-06-08 kello 9 44 01" src="https://github.com/user-attachments/assets/c553a115-6aea-4da1-b6c9-658bb249b346" />
<br>
  <em>Figure 1: IP configuration</em>
</p>

2. Open the LxCameraViewer to test the camera view. Glick the [3D settings] tab. The default camera high exposure value is 650, and the low exposure value is 200. Adjust the camera exposure value based on different application scenarios.

3. Select the pallet positioning algorithm, and set the working mode to close when disconnected. For better recognition, it is recommended to use the updated version of the software, PalletPro, which can be upgraded through firmware updates. ???

## 3.3 Camera connection (PalletPro)

1. Before opening PalletPro, exit LxCameraViewer first. Then open the Pallet Recognition software PalletPro: It is recommended to use the latest version of PalletPro.

2. After opening PalletPro, it will automatically scan the camera. Click on the camera to open and obtain the camera data stream.

3. Click on parameter settings, and the user can get the data easily. If the parameters are all default 0 for the first time, click the adaptive button to get the approximate installation height of the current camera. Then fine-tune it, as shown in the diagram, adjusting the auxiliary line value to the intersection position of the pallet and the ground. Click save parameters, check real-time display, and real-time detection to achieve pallet recognition display functionality.







