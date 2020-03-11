## 自定义设置

用户自定义实现设置模块，参考 [TuyaIPC CameraSDK - 设备功能点](https://tuyainc.github.io/tuyasmart_camera_android_sdk_doc/zh-hans/resource/camera_device_points.html)

**接口说明**

设置 SettingListener 监听，实现自定义面板设置功能，入口在预览面板右上角

```java
TuyaCameraPanelSDK.setCustomSettingListener(SettingListener settingListener);
```

 **参数说明**

| 参数            | 说明                                                         |
| :-------------- | :----------------------------------------------------------- |
| settingListener | SettingListener接口，设置此监听，可自定义云存储面板；可自定义设置面板，不设置则调用默认涂鸦摄像机的设置面板 |

**示例代码**

```java
TuyaCameraPanelSDK.setCustomSettingListener(new SettingListener() {
    @Override
    public void onSettingClick() {
        L.d(TAG, "自定义设置");
    }
});
```