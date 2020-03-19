## 视频流门铃面板

摄像机视频流门铃接听面板，显示推送过来的实时视频流门铃消息界面，包括门铃状态信息，接听，挂断功能；门铃接听有时效性，停留时间 < 25s，接听成功后进行实时视频通话。

**面板类名**

DoorBellDirectCameraActivity.class

 **参数说明**

| 参数              | 说明                                 |
| :---------------- | :----------------------------------- |
| extra_camera_uuid | 设备 id，一般通过推送过来的消息中提取 |
|  doorbell_start_time | long类型，表示按下门铃的开始时间，门铃接听面板从按下开始计时，停留时长为25s（实际 < 25s） |

**示例代码**

```java
Bundle bundle = new Bundle();
bundle.putString("extra_camera_uuid", deviceId);
bundle.putLong("doorbell_start_time", startTime);
Intent intent = new Intent(context, DoorBellDirectCameraActivity.class);
intent.putExtras(bundle);
context.startActivity(intent);
```

**面板示意图**

![面板示意图](./images/camera_panel_video_doorbell.png)