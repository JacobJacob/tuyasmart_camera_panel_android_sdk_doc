## 常见问题

- 通过家庭 id 获取设备 id

  参考 [TuyaHomeSdk - 家庭管理](https://tuyainc.github.io/tuyasmart_home_android_sdk_doc/zh-hans/resource/HomeManager.html)，getHomeDeviceList()

- 通过设备 deviceId 获取设备信息 deviceBean

  ```java
  DeviceBean deviceBean = TuyaHomeSdk.getDataInstance().getDeviceBean(deviceId);
  ```

- 面板内的多语言配置

  可通过下载 Demo 提供的[多语言包](https://github.com/TuyaInc/tuyasmart_camera_panel_android_sdk/tree/master/language/res)，选择自己想要的进行配置
  
- SDK 编译版本

  SDK 编译版本为 28

