## Message-Center Panel

The camera message center panel includes all kinds of messages generated during the recording process of the camera. It is displayed by date and message type. The message category supports pictures, videos, and pure audio. It can be previewed and deleted.

**Panel Class Name**

IPCCameraMessageCenterActivity.class

**Parameter Description**

| Parameter         | Description |
| :---------------- | :---------- |
| extra_camera_uuid | device id   |

**Example Codes**

```java
Intent intent = new Intent(context, IPCCameraMessageCenterActivity.class);
intent.putExtra("extra_camera_uuid", deviceId);
context.startActivity(intent);
```

**Panel Display**

![消息面板](./images/camera_panel_message.png)