## Device icon

Users can modify the camera  icon by themselves.

**Declaration**

Call modifyDeviceImg () under TuyaHomeSdk to modify the device icon

```java
DeviceInfoRepository deviceInfoRepository = new DeviceInfoRepositoryImpl(context);
ModifyDevInfoInteractor mModifyDevInfoInteractor = new ModifyDevInfoInteractorImpl(deviceInfoRepository);
mModifyDevInfoInteractor.modifyDeviceImg( deviceId,  deviceName, imageFile,  callback);
```

 **Parameters**

| Parameter  | Description                                                  |
| :--------- | :----------------------------------------------------------- |
| deviceId   | device id                                                    |
| imageFile  | File , Indicates the image file to be uploaded               |
| deviceName | device name，Available through DeviceBean in the TuyaHomeSdk |
| callback   | ModifyDevInfoInteractor.ModifyDeviceImgCallback interface,uploaded image file success / failure callback |

**Example**

```java
/**
 * modify icon
 *
 * @param context
 * @param deviceId     
 * @param iconFilePath
 */ 
public void uploadIcon(final Context context, String deviceId, String iconFilePath) {
    DeviceBean deviceBean = TuyaHomeSdk.getDataInstance().getDeviceBean(deviceId);
    String panelName = "";
    if (deviceBean != null) {
        panelName = deviceBean.getName();
    }
    DeviceInfoRepository deviceInfoRepository = new DeviceInfoRepositoryImpl(context);
    ModifyDevInfoInteractor mModifyDevInfoInteractor = new ModifyDevInfoInteractorImpl(deviceInfoRepository);
    ProgressUtils.showLoadingViewFullPage(context);
    mModifyDevInfoInteractor.modifyDeviceImg(deviceId, panelName, new File(iconFilePath),
            new ModifyDevInfoInteractor.ModifyDeviceImgCallback() {
                @Override
                public void onModifyDeviceImgSuccess(String url) {
                   
                    ProgressUtils.hideLoadingViewFullPage();
                }

                @Override
                public void onModifyDeviceImgFailure() {
                    
                    ProgressUtils.hideLoadingViewFullPage();
                }
            });
}
```

