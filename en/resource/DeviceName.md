## Device name

Developers can modify camera device name

**Declaration**

Call renameDevice () under TuyaHomeSdk to modify the device name

```java
TuyaHomeSdk.newDeviceInstance(deviceId).renameDevice(String deviceName, IResultCallback callback);
```

 **Parameters**

| Parameter | Description                 |
| :------ | :------------------------------ |
| deviceId   | device id |
| deviceName | device renamed name           |
| callback   | IResultCallback interface，device rename success / failure callback |

**Example**

```java
/**
 * modify name
 * @param context
 * @param deviceId      
 * @param deviceName    
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

