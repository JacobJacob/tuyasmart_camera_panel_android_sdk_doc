## Customize device information under the settings panel

The developer can customize the device icon and name in the Tuya smart camera settings panel.

**Interface Description**

Set DeviceInfoListener and customize the panel to modify device information.

```java
TuyaCameraPanelSDK.setCustomDeviceInfoListener(DeviceInfoListener deviceInfoListener);
```

 **Parameter Description**

| Parameter          | Description                                                  |
| :----------------- | :----------------------------------------------------------- |
| deviceInfoListener | DeviceInfoListener interface, set this listener, can be customized to achieve panel settings-device information function |

**Example Codes**

```java
TuyaCameraPanelSDK.setCustomDeviceInfoListener(new DeviceInfoListener() {
    @Override
    public void onDeviceInfoClick(String deviceId) {
        L.d(TAG, "Customize device information");
    }
});
```

