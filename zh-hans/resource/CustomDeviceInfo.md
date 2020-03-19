## 设置面板 - 自定义设备信息

用户在涂鸦智能摄像机设置面板内去自定义实现设备图标，名称的修改

**接口说明**

设置 DeviceInfoListener 监听，自定义面板去实现设备信息修改

```java
TuyaCameraPanelSDK.setCustomDeviceInfoListener(DeviceInfoListener deviceInfoListener);
```

 **参数说明**

| 参数               | 说明                                                         |
| :----------------- | :----------------------------------------------------------- |
| deviceInfoListener | DeviceInfoListener 接口，设置此监听，可自定义设置实现 面板设置-设备信息功能 |

**示例代码**

```java
TuyaCameraPanelSDK.setCustomDeviceInfoListener(new DeviceInfoListener() {
    @Override
    public void onDeviceInfoClick(String deviceId) {
        L.d(TAG, "设备信息 -自定义实现");
    }
});
```

