## 设备图标

用户可自行修改摄像机设备logo图标

**接口说明**

调用 TuyaHomeSdk 下面的 modifyDeviceImg() 进行设备logo的修改

```java
DeviceInfoRepository deviceInfoRepository = new DeviceInfoRepositoryImpl(context);
ModifyDevInfoInteractor mModifyDevInfoInteractor = new ModifyDevInfoInteractorImpl(deviceInfoRepository);
mModifyDevInfoInteractor.modifyDeviceImg( deviceId,  deviceName, imageFile,  callback);
```

 **参数说明**

| 参数       | 说明                                                         |
| :--------- | :----------------------------------------------------------- |
| deviceId   | 设备id                                                   |
| imageFile  | File类型，表示待上传的图片文件                  |
| deviceName | 设备名称，通过公版 TuyaHomeSdk 的DeviceBean获取              |
| callback   | ModifyDevInfoInteractor.ModifyDeviceImgCallback接口，上传的图片文件成功/失败的回调 |

**示例代码**

```java
/**
 * 修改设备头像
 *
 * @param context
 * @param deviceId     设备id
 * @param iconFilePath 待上传的设备头像地址
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

