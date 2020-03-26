## Overview

Tuya Smart Camera Panel SDK (referred to as: TuyaCameraPanelSDK) provides users with Tuya Camera related panels, which mainly include:

| Class name                           | Description                                                  |
| :----------------------------------- | :----------------------------------------------------------- |
| CameraPanelActivity.class            | Camera native preview panel, mainly including live video preview. |
| CameraPlaybackActivity.class         | Camera playback panel, showing videos stored on the camera storage device. |
| CameraCloudActivity.class            | Camera cloud storage panel, showing the recorded cloud video after the cloud storage function is activated. |
| LocalPhotoOrVideoActivity.class      | Camera album panel, which shows the screenshot or recorded video file saved according to the device id. |
| IPCCameraMessageCenterActivity.class | Camera message center panel, including various detection alarm messages generated during camera recording. |
| CameraSettingActivity.class          | Camera settings panel, including device information, basic settings, storage settings, restart device, restart device and other commonly used camera functions. |
| DoorBellCallingActivity.class        | Camera doorbell panel,show the static screen that pops up after receiving the doorbell message, including the answer and end function. |
| DoorBellDirectCameraActivity.class   | Camera video doorbell panel,show the real-time video picture pushed by doorbell message, including answering and ending functions, with timeliness. |