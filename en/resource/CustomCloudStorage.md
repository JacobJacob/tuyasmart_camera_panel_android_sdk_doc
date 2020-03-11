## Customize cloud storage

User-defined cloud storage,refer to [TuyaIPCCameraSDK - CloudStorage](<https://tuyainc.github.io/tuyasmart_camera_android_sdk_doc/en/resource/CloudStorageProcess.html>)

**Interface Description**

Set up CloudStoragePanelListener, customize the panel to implement cloud storage video playback.

```java
TuyaCameraPanelSDK.setCustomCloudStoragePanelListener(CloudStoragePanelListener cloudStoragePanelListener);
```

 **Parameter Description**

| Parameter                 | Description                                                  |
| :------------------------ | :----------------------------------------------------------- |
| cloudStoragePanelListener | CloudStoragePanelListener interface, set this listener to customize the cloud storage panel; if not set, skip to the default Tuya camera cloud storage panel |

**Example Codes**

```java
TuyaCameraPanelSDK.setCustomCloudStoragePanelListener(new CloudStoragePanelListener() {
    @Override
    public void onCloudStoragePanelClick(String deviceId) {
        L.d(TAG, "Customize cloud storage " + deviceId);
    }
});
```
