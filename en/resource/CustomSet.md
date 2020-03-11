## Customize Set

User-defined implementation setting module, refer to [TuyaIPCCameraSDK - Set](<https://tuyainc.github.io/tuyasmart_camera_android_sdk_doc/en/resource/camera_device_points.html>)

**Interface Description**

Set SettingListener to implement the custom panel setting function. The entrance is in the upper right corner of the preview panel.

```java
TuyaCameraPanelSDK.setCustomSettingListener(SettingListener settingListener);
```

 **Parameter Description**

| Parameter       | Description                                                  |
| :-------------- | :----------------------------------------------------------- |
| settingListener | SettingListener interface, set this listener, you can customize the cloud storage panel; you can customize the settings panel, if not set, call the settings panel of the default Tuya camera |

**Example Codes**

```java
TuyaCameraPanelSDK.setCustomSettingListener(new SettingListener() {
    @Override
    public void onSettingClick() {
        L.d(TAG, "Customize Set");
    }
});
```