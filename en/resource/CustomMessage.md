## Customize Message Center

User-defined implementation of message center panel,reference [Tuya Smart Camera SDK - Message Center](https://tuyainc.github.io/tuyasmart_camera_android_sdk_doc/en/resource/message_center_list.html)

**Declaration**

Set up MessagePanelListener and customize the panel to display message center data

```java
TuyaCameraPanelSDK.setCustomMessagePanelListener(MessagePanelListener messagePanelListener);
```

 **Parameters**

| Parameter            | Description                                                  |
| :------------------- | :----------------------------------------------------------- |
| messagePanelListener | MessagePanelListener interface, set this listener to customize the message center; if not set, skip to the default graffiti camera message center panel |

**Example**

```java
TuyaCameraPanelSDK.setCustomMessagePanelListener(new MessagePanelListener() {
    @Override
    public void onMessagePanelClick(String deviceId) {
        L.d(TAG, "Customize Message Center " + deviceId);
    }
});
```
