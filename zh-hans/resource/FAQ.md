## 常见问题

- 通过家庭id 获取 设备id

  参考 [TuyaHomeSdk - 家庭管理](https://tuyainc.github.io/tuyasmart_home_android_sdk_doc/zh-hans/resource/HomeManager.html)，getHomeDeviceList()

- 通过设备 deviceId 获取设备信息 deviceBean

  ```java
  DeviceBean deviceBean = TuyaHomeSdk.getDataInstance().getDeviceBean(deviceId);
  ```

