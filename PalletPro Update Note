# PalletPro Update Note

**Version:** 1.4.8  
**Release Date:** 2026.08.21

---

# PalletPro English Translation Fixes

This document lists the English text added for interface elements that previously remained untranslated in English mode, together with the existing English wording refined during the same update.

## Existing English Wording Refinements

| Interface context | Previous English text | Final English text |
| --- | --- | --- |
| Height adaptation button | High Adaptability | Auto-adjusting height |
| Parameter settings section | Parameter Settings | Camera Position Settings |
| Installation method: upright | Upstanding | Upstanding(logo on top) |
| Installation method: left-mounted | Left side | Roll left 90 degrees |
| Installation method: inverted | Upside Down | Upside down |
| Installation method: right-mounted | Right side | Roll right 90 degrees |

## 1. Main Window and Status Log

### Interface text

- Get Trajectory
- Firmware Upgrade
- Low-FPS
- High-FPS
- Dock Operation
- External Calibration
- Language

### Status log text

| Context | Final English text |
| --- | --- |
| Low frame-rate mode selected | Switched to Low-FPS mode |
| High frame-rate mode selected | Switched to High-FPS mode |
| Euler-angle output | Euler angles: `%1 %2 %3` |
| Current camera address | Current IP: `%1` |
| Trajectory download started | Starting to download file `[%1]` |
| Trajectory download succeeded | File `[%1]` downloaded successfully |
| Trajectory download failed | Failed to download file `[%1]` |

## 2. Common Dialogs and Firmware Upgrade

| Context | Final English text |
| --- | --- |
| General reminder title | Notice |
| Warning title | Warning |
| Information title | Information |
| Language prompt | Please choose a language: |
| Language-dialog cancel button | Cancel |
| Invalid folder input | Invalid folder input, please check |
| Invalid camera address | Invalid IP Address! |
| Camera search required | Please search for a camera first. |
| Camera unavailable during firmware upgrade | Camera is not connected or running! |
| Firmware file-selection title | Select Firmware File |
| Firmware file filter | Firmware Files (`*.bin`) |
| Firmware upgrade status | Firmware file: `%1`, upgrading... |
| Timed reminder title | Notice CLOSE IN `%1` MS |
| Model training succeeded | Model Trained Success! |
| Model training failed | Model Trained Failed! |

## 3. Camera Internal Window

### Controls

- Camera Internal
- Camera Operations
- Camera IP
- Camera ID
- Embedded Version
- Download lanxin_vision Logs
- Embedded Algorithm Upgrade
- Parameter Editing
- Download Application Parameters
- Reboot Camera
- Edit Application Parameters
- Upload
- Restart the camera after changing APP settings.
- Algorithm Parameters (Advanced)
- Download
- Edit Algorithm Parameters
- Select File to Upload
- Open Folder

### Parameter creation and editing options

- Select the creation type
- Edit Custom Parameters
- Plane Detection
- Cage Stacking
- Reel Docking

### File and camera-operation messages

| Context | Final English text |
| --- | --- |
| File download started | Downloading file `[%1]` |
| Local output directory | Local path: `%1` |
| File download succeeded | File `[%1]` downloaded successfully |
| File download failed | Failed to download file `[%1]` |
| File creation succeeded | File created successfully |
| File creation failed | Failed to create file |
| APP settings path update failed | Failed to update the APP settings path. |
| Configuration path update failed | Failed to update config_path in file `[%1]` |
| Algorithm template created | Algorithm template parameter file created successfully |
| Algorithm template creation failed | Failed to create the algorithm template parameter file |
| Hand-eye calibration file created | Hand-eye calibration file created successfully |
| Missing creation type | Please select a file type to create |
| File upload succeeded | File `[%1]` uploaded successfully |
| File upload failed | Failed to upload file `[%1]` |
| Invalid firmware file | Please select the correct firmware file (`*.bin`). |
| Template creation title | Created Successfully |
| Template creation result | Template file created successfully! |
| Template creation failure title | Template Creation Failed |
| Template path or permission error | Please check the file path and permissions. |
| Camera reboot started title | Camera Reboot Started |
| Camera reboot progress | The camera is rebooting... |
| Camera reboot failed title | Camera Reboot Failed |
| Camera reboot connection error | Please check the camera connection. |
| APP settings path synchronized | The path has been synchronized to app_setting.json. |

## 4. Pallet Teaching and Calibration Messages

| Context | Final English text |
| --- | --- |
| Generic far-end calibration failure | Far-end calibration error; error_code=`%1` |
| Far-end ground detection failed | Far-end ground detection failed! Please retry |
| Far-end pallet positioning failed | Far-end pallet positioning failed! Please retry |
| Pallet angle exceeded | Pallet placement angle is too large; it must not exceed 3.5 degrees |
| Teaching positions too close | Pallet is too close to the near-end teaching position; minimum distance is 0.5 m |
| Teaching positions too far apart | Pallet is too far from the near-end teaching position; maximum distance is 2.5 m |
| Far-end teaching failed after correction | Far-end pallet teaching failed after angle correction. Please retry, or try another pallet. |
| Secondary calibration completed | Secondary calibration completed |

## 5. Calibration Instructions Window

### Controls

- Calibration
- Instructions
- Please review and confirm the following information
- Client name (English + ID)
- Minimum detection distance (greater than camera-to-fork-tip distance, mm)
- OK
- Cancel

### Single-pallet teaching instructions

- Single-pallet teaching
- Ensure the floor is level and its imaging data is complete.
- Keep the pallet facing the camera and forks, and horizontally centered.
- Place the pallet center about 1.5 m from the camera.
- Keep both forks at approximately the same distance from the pallet.
- Place the pallet level on the floor and align the center fork with the camera optical center.

### Two-pallet teaching instructions

- Two-pallet secondary teaching (for noticeable pitch angles)
- Perform the first teaching in the same way as single-pallet teaching.
- Place the pallet center about 1.5 m along the camera optical axis.
- After the first teaching succeeds, move the pallet or forklift while minimizing lateral displacement.
- A distance of more than 1 m between the two teaching positions is recommended.

## 6. Advanced Parameter Settings Window

### Controls

- Advanced Parameter Settings
- Configuration File
- Camera IP/ID
- Save Parameters
- Advanced Parameters
- Leg Width
- Crossbar Detection
- Pallet Width
- Parameter
- Value
- Description

### Leg-width options

- Standard 10-15 cm
- Thin Leg 5 cm
- Slim Pallet 3-4 cm
- Wide 15 cm
- Extra Wide 20 cm+
- 8-32 cm
- Custom

### Crossbar options

- Standard
- Thin (80%)
- Very Thin (60%)
- Sparse (10%)

### Pallet-width options

- Standard 0.7-1.3 m
- Wide Pallet 1.1-1.6 m
- Custom

### Save and validation messages

| Context | Final English text |
| --- | --- |
| Local file save failed | Failed to save the local file. |
| Local file save succeeded | The local file was saved successfully. |
| Invalid parameter configuration | Invalid parameter configuration. Please check the file path. |

### Parameter descriptions

| Parameter key | Final English description |
| --- | --- |
| `R` | Euler angles |
| `t` | Translation vector |
| `ground_y` | Ground height (mm) |
| `fork_space` | Camera-to-fork clearance |
| `min_leg` | Minimum pallet-leg width |
| `max_leg` | Maximum pallet-leg width |
| `multi_level` | Enable multi-level pallet detection |
| `level_height` | Single-level pallet height |
| `x-client` | Customer name |
| `orientation` | Mounting: 0 upright, 2 inverted, 1/3 side-mounted |
| `min_z` | Minimum Z value |
| `max_z` | Maximum Z value |
| `min_x` | Minimum horizontal value |
| `max_x` | Maximum horizontal value |
| `two_leg` | Enable two-leg pallets |
| `quad` | Enable four-leg pallets |
| `thickness` | Detection slice thickness |
| `scan_step` | Sampling step |
| `leg_dist_min` | Minimum two-leg distance |
| `leg_dist_max` | Maximum two-leg distance |
| `bar_percent` | Crossbar fill percentage |
| `space_dist` | Minimum segmentation distance |
| `min_line_count` | Minimum line-point count |
| `log_level` | Log level |
| `cutting_height` | Cutting height |
| `max_legwidth_diff` | Maximum left/right leg-width difference |
| `min_hole` | Minimum pallet-hole width |
| `max_hole` | Maximum pallet-hole width |
| `denoise_search_radius` | Denoising search radius |
| `denoise_min_pts` | Minimum denoising neighbors |
| `bar_check_dist` | Crossbar validation distance |
| `bar_search_y` | Crossbar search distance |
| `max_hole_diff` | Maximum pallet-hole spacing difference |
| `fork_angle` | Angle between forks and travel direction |
| `fork_insert` | Extra insertion distance after reaching pallet front |
| `angle_limit` | Pallet angle limit |
| `search_height` | Search height |
| `ground_extra_h0` | Lower ground-search offset |
| `ground_extra_h1` | Upper ground-search offset |
| `max_filter_incline` | Maximum filtering inclination |
| `max_incline` | Maximum pallet inclination |
| `show_projected` | Show projected result |
| `reflect_rectify` | Enable reflection rectification |
| `height_method` | Height calculation method |

## 7. Algorithm Parameter Dialogs

### Common controls

- Import Parameters
- Export Parameters
- Save Parameters
- Confirm
- Basic Information
- File
- Customer Name (English or Pinyin)
- Algorithm Configuration
- Plane Width
- Region Selection (Maximum)
- Region Selection (Minimum)

### Dialog and algorithm names

- Plane Detection Algorithm
- Cage Stacking Algorithm
- Reel Docking Algorithm
- Plane Detection Parameters
- Cage Stacking Parameters
- Reel Docking Parameters

### File messages

| Context | Final English text |
| --- | --- |
| Empty output path | The file path is empty. Please export the parameters first. |
| Missing output file | The file does not exist. Please export the parameters first. |
| File save failed | Failed to save the file. Please check the path. |
| File save succeeded | File saved successfully. |

## 8. Structured JSON Editor

### Controls and status text

- Structured JSON Editor V2024 (Chinese content is not supported)
- Create Algorithm Parameters
- Select an Algorithm
- Click to Show Text
- Ready
- Add Field
- Select Type
- OK
- Cancel

### Validation and operation messages

| Context | Final English text |
| --- | --- |
| Bounding box required | Please select a bounding-box region first. |
| Required fields missing | Please check whether the following fields are missing |
| Invalid JSON | Invalid JSON format. Please check it. |
| JSON saved | JSON saved successfully |
| Input error title | Input Error |
| Incomplete key-value pair | The key-value pair is incomplete. |
| Duplicate key-value pair | The key-value pair already exists. |
| Invalid integer | Please enter a valid integer. |
| Invalid Boolean | Please enter true/false or 1/0. |
| Invalid floating-point value | Please enter a valid floating-point number. |
| Invalid type | Please select a valid type. |
| Input result title | Input Result |
| Value type | Type |
| No key selected | Please select a key to delete. |
| Delete confirmation | Delete key `%1`? |
| Delete success title | Deleted |
| Deleted key result | The key was deleted. |
| Missing key | The key does not exist. |
| Algorithm creation confirmation | Create parameters for the selected algorithm? |
| Empty default parameters | The default parameters are empty. |
| Algorithm initialization failed | Failed to initialize the selected algorithm. |
| Empty calibration result | The current calibration result is empty. |
| Workstation selection title | Workstation Selection |
| Workstation selection prompt | Please select a workstation. |
| First workstation | Workstation 1 |
| Second workstation | Workstation 2 |
| Selection result title | Selection |
| Selection cancelled | Selection cancelled. |
| Invalid or empty file | The file is empty or invalid. Please check it. |
| Error details | Error |

## 9. Config Tools Parameter Descriptions

| Parameter key | Final English description |
| --- | --- |
| `app_id` | Algorithm ID |
| `tcp_port` | TCP port |
| `config_path` | Algorithm configuration path on camera |
| `desc` | File description |
| `client` | Customer name |
| `time` | Time |
| `R` | Euler angles (rx, ry, rz) |
| `t` | Translation vector |
| `filters` | Filtering parameters |
| `leafsize` | Downsampling leaf size |
| `box_max` | Bounding-box maximum |
| `box_min` | Bounding-box minimum |
| `min_size` | Minimum point-cloud size |
| `tolerance` | Minimum segmentation distance |
| `min_max_thr` | Plane width range |
| `level_dist` | Single-level height threshold |
| `pixel_mm` | 2D projection scale |
| `num` | Workstation number |
| `seat` | Workstation bounding box and calibration |
| `transf` | Hand-eye calibration frame |
| `tool` | Tool coordinate frame |
| Unmapped parameter-description fallback | Parameter: `<key>` |

---

# PalletPro 未翻译内容及英文措辞修复对照

本文记录英文模式下原来仍显示中文、由本次代码补充英文翻译的内容，以及本次调整过的已有英文措辞。

## 现有英文措辞调整

| 中文含义 | 修改前的英文 | 修改后的英文 |
| --- | --- | --- |
| 高度自适应 | High Adaptability | Auto-adjusting height |
| 参数设置 | Parameter Settings | Camera Position Settings |
| 安装方式：正装 | Upstanding | Upstanding(logo on top) |
| 安装方式：左装 | Left side | Roll left 90 degrees |
| 安装方式：倒装 | Upside Down | Upside down |
| 安装方式：右装 | Right side | Roll right 90 degrees |

## 1. PalletPro 主界面及状态日志

| 中文 | 修改后的英文 |
| --- | --- |
| 获取轨迹 | Get Trajectory |
| 固件升级 | Firmware Upgrade |
| 低频刷新 | Low-FPS |
| 高频刷新 | High-FPS |
| 对接操作 | Dock Operation |
| 外参标定 | External Calibration |
| 语言/Language | Language |
| 已切换成低频模式 | Switched to Low-FPS mode |
| 已切换成高频模式 | Switched to High-FPS mode |
| 欧拉角 %1 %2 %3 | Euler angles: %1 %2 %3 |
| 当前 IP：%1 | Current IP: %1 |
| 开始获取文件 [%1] | Starting to download file [%1] |
| 文件 [%1] 获取成功 | File [%1] downloaded successfully |
| 文件 [%1] 获取失败 | Failed to download file [%1] |

## 2. 通用提示框及固件升级

| 中文 | 修改后的英文 |
| --- | --- |
| 温馨提示 | Notice |
| 警告 | Warning |
| 提示 | Information |
| 请选择语言/Please choose language: | Please choose a language: |
| 取消/Cancel | Cancel |
| 文件夹输入错误，请检查 | Invalid folder input, please check |
| 无效 IP 地址 | Invalid IP Address! |
| 请扫描相机 | Please search for a camera first. |
| 相机未连接或未运行！ | Camera is not connected or running! |
| 升级文件 | Select Firmware File |
| SO 文件（*.bin）/固件文件（*.bin） | Firmware Files (*.bin) |
| 固件文件：%1 升级中 | Firmware file: %1, upgrading... |
| 温馨提示 CLOSE IN %1 MS | Notice CLOSE IN %1 MS |

## 3. Camera Internal 窗口

### 3.1 控件文字

| 中文 | 修改后的英文 |
| --- | --- |
| 相机内部设置 | Camera Internal |
| 相机操作 | Camera Operations |
| 相机 IP | Camera IP |
| 相机 ID | Camera ID |
| 嵌入式版本 | Embedded Version |
| 获取 lanxin_vision 日志 | Download lanxin_vision Logs |
| 嵌入式算法升级 | Embedded Algorithm Upgrade |
| 参数编辑 | Parameter Editing |
| 获取应用参数（APP_Setting） | Download Application Parameters |
| 重启相机 | Reboot Camera |
| 编辑应用参数（APP_Setting） | Edit Application Parameters |
| 上传 | Upload |
| 修改 APP_setting 后需重启相机生效 | Restart the camera after changing APP settings |
| 算法参数（高级） | Algorithm Parameters (Advanced) |
| 获取 | Download |
| 编辑算法参数 | Edit Algorithm Parameters |
| 选择文件上传 | Select File to Upload |
| 打开目录 | Open Folder |

### 3.2 创建、编辑参数选项

| 中文 | 修改后的英文 |
| --- | --- |
| 选择创建类型 | Select the creation type |
| 编辑定制参数 | Edit Custom Parameters |
| 平面检测 | Plane Detection |
| 料笼堆叠 | Cage Stacking |
| 卷轴对接 | Reel Docking |

### 3.3 文件及相机操作提示

| 中文 | 修改后的英文 |
| --- | --- |
| 开始获取文件 [%1] | Downloading file [%1] |
| 本地路径：%1 | Local path: %1 |
| 文件 [%1] 获取成功 | File [%1] downloaded successfully |
| 文件 [%1] 获取失败 | Failed to download file [%1] |
| 文件创建成功 | File created successfully |
| 文件创建失败 | Failed to create file |
| app settings 路径更新失败 | Failed to update the APP settings path. |
| 文件 [%1] 修改 config_path 失败 | Failed to update config_path in file [%1] |
| 算法模板参数文件创建成功 | Algorithm template parameter file created successfully |
| 算法模板参数文件创建失败 | Failed to create the algorithm template parameter file |
| 手眼标定文件创建成功 | Hand-eye calibration file created successfully |
| 请点击选择创建文件类型 | Please select a file type to create |
| 文件 [%1] 上传成功 | File [%1] uploaded successfully |
| 文件 [%1] 上传失败 | Failed to upload file [%1] |
| 请选取正确的固件（*.bin） | Please select the correct firmware file (*.bin). |
| 创建成功 | Created Successfully |
| 模板文件创建成功 | Template file created successfully! |
| 模板创建失败 | Template Creation Failed |
| 请检查文件路径和权限 | Please check the file path and permissions. |
| 重启相机成功 | Camera Reboot Started |
| 相机正在重启 | The camera is rebooting... |
| 相机重启失败 | Camera Reboot Failed |
| 请检查相机连接 | Please check the camera connection. |
| 路径已同步到 app_setting.json | The path has been synchronized to app_setting.json. |

## 4. Pallet Teaching 与标定提示

| 中文 | 修改后的英文 |
| --- | --- |
| 远端标定异常；error_code=%1 | Far-end calibration error; error_code=%1 |
| 远端地面检测失败！请重试 | Far-end ground detection failed! Please retry |
| 远端定位托盘失败！请重试 | Far-end pallet positioning failed! Please retry |
| 托盘摆放角度偏大，不要超过 3.5 度 | Pallet placement angle is too large; it must not exceed 3.5 degrees |
| 托盘距离近端示教距离过近，至少需要 0.5 米 | Pallet is too close to the near-end teaching position; minimum distance is 0.5 m |
| 托盘距离近端示教距离过远，不能超过 2.5 米 | Pallet is too far from the near-end teaching position; maximum distance is 2.5 m |
| 角度修正后远端托盘示教失败，请重试！换个托盘？ | Far-end pallet teaching failed after angle correction. Please retry, or try another pallet. |
| 二次标定完成 | Secondary calibration completed |

## 5. 标定须知窗口

| 中文 | 修改后的英文 |
| --- | --- |
| 标定窗口 | Calibration |
| >>> 注意事项 <<< | >>> Instructions <<< |
| 请修改并确认如下信息 | Please review and confirm the following information |
| 客户名称（英文+ID） | Client name (English + ID) |
| 识别最近距离（需大于相机到叉尖距离，单位 mm） | Minimum detection distance (greater than camera-to-fork-tip distance, mm) |
| 确定 | OK |
| 取消 | Cancel |
| 单托盘示教方案 | Single-pallet teaching |
| 首先保证地面平整，且地面成像数据完整 | Ensure the floor is level and its imaging data is complete. |
| 保证托盘正对相机、叉臂，且水平居中 | Keep the pallet facing the camera and forks, and horizontally centered. |
| 托盘中心距离相机约 1.5 米 | Place the pallet center about 1.5 m from the camera. |
| 双叉臂距离托盘距离基本相同 | Keep both forks at approximately the same distance from the pallet. |
| 托盘水平放到地面，中间叉臂与相机光心对齐 | Place the pallet level on the floor and align the center fork with the camera optical center. |
| 双托盘二次示教方案（适合有明显俯仰角的情况） | Two-pallet secondary teaching (for noticeable pitch angles) |
| 首次示教同单托盘示教类似 | Perform the first teaching in the same way as single-pallet teaching. |
| 托盘中心距离相机光线约 1.5 米 | Place the pallet center about 1.5 m along the camera optical axis. |
| 首次示教成功后，移动托盘或叉车，尽量减少叉车和托盘的横移变化 | After the first teaching succeeds, move the pallet or forklift while minimizing lateral displacement. |
| 两次示教距离推荐在 1 米以上 | A distance of more than 1 m between the two teaching positions is recommended. |

## 6. Advanced Parameter Settings 窗口

### 6.1 控件和选项

| 中文 | 修改后的英文 |
| --- | --- |
| 高级参数设置 | Advanced Parameter Settings |
| 读取地址 | Configuration File |
| 相机 IP/ID | Camera IP/ID |
| 保存参数 | Save Parameters |
| 扩展参数 | Advanced Parameters |
| 腿宽选择 | Leg Width |
| 横杆检测 | Crossbar Detection |
| 托盘宽度 | Pallet Width |
| 参数名 | Parameter |
| 参数值 | Value |
| 参数注释 | Description |
| 标准模式 10-15 cm | Standard 10-15 cm |
| 细腿模式 5 cm | Thin Leg 5 cm |
| 纤细托盘 3-4 cm | Slim Pallet 3-4 cm |
| 偏宽 15 cm | Wide 15 cm |
| 超宽 20 cm+ | Extra Wide 20 cm+ |
| 8~32 cm | 8-32 cm |
| 自定义 | Custom |
| 标准 | Standard |
| 较细（80%） | Thin (80%) |
| 非常细（60%） | Very Thin (60%) |
| 稀少（10%） | Sparse (10%) |
| 标准模式 0.7~1.3 m | Standard 0.7-1.3 m |
| 宽托盘 1.1~1.6 m | Wide Pallet 1.1-1.6 m |
| 本地文件保存失败 | Failed to save the local file. |
| 本地文件保存成功 | The local file was saved successfully. |
| 输入参数配置有误，请检查路径文件 | Invalid parameter configuration. Please check the file path. |

### 6.2 本次补充的高级参数说明

| 参数 | 修改后的英文说明 |
| --- | --- |
| `R` | Euler angles |
| `t` | Translation vector |
| `ground_y` | Ground height (mm) |
| `fork_space` | Camera-to-fork clearance |
| `min_leg` | Minimum pallet-leg width |
| `max_leg` | Maximum pallet-leg width |
| `multi_level` | Enable multi-level pallet detection |
| `level_height` | Single-level pallet height |
| `x-client` | Customer name |
| `orientation` | Mounting: 0 upright, 2 inverted, 1/3 side-mounted |
| `min_z` | Minimum Z value |
| `max_z` | Maximum Z value |
| `min_x` | Minimum horizontal value |
| `max_x` | Maximum horizontal value |
| `two_leg` | Enable two-leg pallets |
| `quad` | Enable four-leg pallets |
| `thickness` | Detection slice thickness |
| `scan_step` | Sampling step |
| `leg_dist_min` | Minimum two-leg distance |
| `leg_dist_max` | Maximum two-leg distance |
| `bar_percent` | Crossbar fill percentage |
| `space_dist` | Minimum segmentation distance |
| `min_line_count` | Minimum line-point count |
| `log_level` | Log level |
| `cutting_height` | Cutting height |
| `max_legwidth_diff` | Maximum left/right leg-width difference |
| `min_hole` | Minimum pallet-hole width |
| `max_hole` | Maximum pallet-hole width |
| `denoise_search_radius` | Denoising search radius |
| `denoise_min_pts` | Minimum denoising neighbors |
| `bar_check_dist` | Crossbar validation distance |
| `bar_search_y` | Crossbar search distance |
| `max_hole_diff` | Maximum pallet-hole spacing difference |
| `fork_angle` | Angle between forks and travel direction |
| `fork_insert` | Extra insertion distance after reaching pallet front |
| `angle_limit` | Pallet angle limit |
| `search_height` | Search height |
| `ground_extra_h0` | Lower ground-search offset |
| `ground_extra_h1` | Upper ground-search offset |
| `max_filter_incline` | Maximum filtering inclination |
| `max_incline` | Maximum pallet inclination |
| `show_projected` | Show projected result |
| `reflect_rectify` | Enable reflection rectification |
| `height_method` | Height calculation method |

## 7. 算法参数窗口

| 中文 | 修改后的英文 |
| --- | --- |
| 导入参数 | Import Parameters |
| 导出参数 | Export Parameters |
| 保存参数 | Save Parameters |
| 确定 | Confirm |
| 基本信息 | Basic Information |
| 文件 | File |
| 客户名称（英文或拼音） | Customer Name (English or Pinyin) |
| 算法配置 | Algorithm Configuration |
| 平面宽度 | Plane Width |
| 区域选择（最大） | Region Selection (Maximum) |
| 区域选择（最小） | Region Selection (Minimum) |
| 平面检测算法 | Plane Detection Algorithm |
| 料笼堆叠算法 | Cage Stacking Algorithm |
| 卷轴对接算法 | Reel Docking Algorithm |
| 平面检测参数 | Plane Detection Parameters |
| 料笼堆叠参数 | Cage Stacking Parameters |
| 卷轴对接参数 | Reel Docking Parameters |
| 文件路径为空，请选择导出参数 | The file path is empty. Please export the parameters first. |
| 文件不存在，请选择导出参数 | The file does not exist. Please export the parameters first. |
| 文件保存失败，请检查路径 | Failed to save the file. Please check the path. |
| 文件保存成功 | File saved successfully. |

## 8. Structured JSON Editor

| 中文 | 修改后的英文 |
| --- | --- |
| 结构化 JSON 编辑工具 V2024（不支持中文） | Structured JSON Editor V2024 (Chinese content is not supported) |
| 创建算法参数 | Create Algorithm Parameters |
| 选择算子 | Select an Algorithm |
| 点击显示文本 | Click to Show Text |
| 启动完成 | Ready |
| 请先选择包围框区域 | Please select a bounding-box region first. |
| 请检查是否缺少以下字段 | Please check whether the following fields are missing |
| JSON 格式错误，请检查 | Invalid JSON format. Please check it. |
| JSON 保存成功 | JSON saved successfully |
| 增加字段 | Add Field |
| 选择类型 | Select Type |
| 输入错误 | Input Error |
| 输入键值对不完整 | The key-value pair is incomplete. |
| 输入键值对已存在 | The key-value pair already exists. |
| 请输入有效的整数 | Please enter a valid integer. |
| 请输入 true/false 或 1/0 | Please enter true/false or 1/0. |
| 请输入有效的浮点数 | Please enter a valid floating-point number. |
| 请输入正确的类型 | Please select a valid type. |
| 输入结果 | Input Result |
| 类型 | Type |
| 请选择要删除的键 | Please select a key to delete. |
| 确定删除键 %1 吗 | Delete key %1? |
| 删除成功 | Deleted |
| 键已删除 | The key was deleted. |
| Key 不存在 | The key does not exist. |
| 确定创建当前算子参数 | Create parameters for the selected algorithm? |
| 默认参数为空 | The default parameters are empty. |
| 当前算子初始化失败 | Failed to initialize the selected algorithm. |
| 当前标定结果为空 | The current calibration result is empty. |
| 工位选择 | Workstation Selection |
| 请选择工位 | Please select a workstation. |
| 工位 1 | Workstation 1 |
| 工位 2 | Workstation 2 |
| 选择结果 | Selection |
| 取消选择 | Selection cancelled. |
| 文件为空或格式错误，请检查 | The file is empty or invalid. Please check it. |
| 错误信息 | Error |

## 9. 本次补充的 Config Tools 参数说明

| 中文说明 | 修改后的英文说明 |
| --- | --- |
| 算法 ID | Algorithm ID |
| TCP 端口 | TCP port |
| 相机内算法配置文件路径 | Algorithm configuration path on camera |
| 本文件描述 | File description |
| 客户名称 | Customer name |
| 时间 | Time |
| 欧拉角（rx, ry, rz） | Euler angles (rx, ry, rz) |
| 平移向量 | Translation vector |
| 滤波参数 | Filtering parameters |
| 降采样大小 | Downsampling leaf size |
| 包围框最大值 | Bounding-box maximum |
| 包围框最小值 | Bounding-box minimum |
| 点云最小数量 | Minimum point-cloud size |
| 分割最小距离 | Minimum segmentation distance |
| 平面宽度范围 | Plane width range |
| 单层高度阈值 | Single-level height threshold |
| 2D 投影比例 | 2D projection scale |
| 工位序号 | Workstation number |
| 工位包围框和标定结果 | Workstation bounding box and calibration |
| 手眼标定坐标系 | Hand-eye calibration frame |
| 工具坐标系 | Tool coordinate frame |
| 未配置的中文参数说明 | Parameter: `<key>` |
