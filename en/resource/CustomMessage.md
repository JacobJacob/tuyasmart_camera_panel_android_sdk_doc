## Customize Message Center

User-defined implementation of message center panel,reference [TuyaCameraSDK - Message Center](https://tuyainc.github.io/tuyasmart_camera_android_sdk_doc/en/resource/message_center_list.html)

**Interface Description**

Set up MessagePanelListener and customize the panel to display message center data

```java
TuyaCameraPanelSDK.setCustomMessagePanelListener(MessagePanelListener messagePanelListener);
```

 **Parameter Description**

| Parameter            | Description                                                  |
| :------------------- | :----------------------------------------------------------- |
| messagePanelListener | MessagePanelListener interface, set this listener to customize the message center; if not set, skip to the default graffiti camera message center panel |

**Example Codes**

```java
TuyaCameraPanelSDK.setCustomMessagePanelListener(new MessagePanelListener() {
    @Override
    public void onMessagePanelClick(String deviceId) {
        L.d(TAG, "Customize Message Center " + deviceId);
    }
});
```