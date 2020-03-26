## 面板概述

涂鸦智能摄像机面板 SDK（简称：TuyaCameraPanelSDK）为方便开发者，减少摄像机面板开发成本，提供了涂鸦摄像机相关的面板，主要包括：



| 类名                                 | 说明                                                         |
| :----------------------------------- | :------------------------------------------------------------- |
| CameraPanelActivity.class            | 摄像机原生预览面板，主要包括视频实时预览。                   |
| CameraPlaybackActivity.class         | 摄像机回放面板，展示的是保存在摄像机存储设备上的视频。       |
| CameraCloudActivity.class            | 摄像机云存储面板，展示开通云存储功能之后录制保存的云端视频。 |
| LocalPhotoOrVideoActivity.class      | 摄像机相册面板，展示的是根据设备 id 所保存的截图或者录制的视频文件。 |
| IPCCameraMessageCenterActivity.class | 摄像机消息中心面板，包括摄像机录制过程中产生的各类侦测告警消息。 |
| CameraSettingActivity.class          | 摄像机设置面板，包括设备信息，基础设置，存储设置，重启设备，重启设备等常用摄像机功能。 |
| DoorBellCallingActivity.class        | 摄像机门铃接听面板，展示接收到门铃消息之后弹出的静态画面，包含接听挂断功能。 |
| DoorBellDirectCameraActivity.class   | 摄像机实时视频流门铃接听面板，展示门铃消息推送过来的实时视频画面，包括接听，挂断功能，具有时效性。 |

