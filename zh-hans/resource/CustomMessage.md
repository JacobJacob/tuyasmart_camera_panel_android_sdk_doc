## 自定义消息中心

用户自定义实现消息中心面板，参考 [Tuya Smart Camera SDK - 消息中心](https://tuyainc.github.io/tuyasmart_camera_android_sdk_doc/zh-hans/resource/message_center_list.html)

**接口说明**

设置 MessagePanelListener 监听，自定义面板去实现消息中心数据的展示

```java
TuyaCameraPanelSDK.setCustomMessagePanelListener(MessagePanelListener messagePanelListener);
```

 **参数说明**

| 参数                 | 说明                                                         |
| :------------------- | :----------------------------------------------------------- |
| messagePanelListener | MessagePanelListener 接口，设置此监听，可自定义消息中心；不设置则跳转到默认涂鸦摄像机消息中心面板 |

**示例代码**

```java
TuyaCameraPanelSDK.setCustomMessagePanelListener(new MessagePanelListener() {
    @Override
    public void onMessagePanelClick(String deviceId) {
        L.d(TAG, "消息中心面板 -自定义实现" + deviceId);
    }
});
```
