## 设备名称

用户可自行修改摄像机设备名称

**接口说明**

调用 TuyaHomeSdk 下面的 renameDevice() 进行设备名称的修改

```java
TuyaHomeSdk.newDeviceInstance(deviceId).renameDevice(String deviceName, IResultCallback callback);
```

 **参数说明**

| 参数    | 说明                            |
| :------ | :------------------------------ |
| deviceId   | 设备id |
| deviceName | 设备重命名的名称                               |
| callback   | IResultCallback接口，设备重命名成功/失败的回调   |

**示例代码**

```java
/**
 * 修改设备名称
 * @param context
 * @param deviceId      设备id
 * @param deviceName    设备重命名名称
 */
public void renameDevice(final Context context, String deviceId, String deviceName) {
    ITuyaDevice mDevice = TuyaHomeSdk.newDeviceInstance(deviceId);
    mDevice.renameDevice(deviceName, new IResultCallback() {
        @Override
        public void onError(String code, String error) {
            
        }

        @Override
        public void onSuccess() {
            
        }
    });
}
```

