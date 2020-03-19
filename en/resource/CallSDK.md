## Use TuyaCameraPanelSDK

TuyaCameraPanelSDK is an external public interface of Tuya Smart Camera Panel SDK, which includes jump and custom implementation of multiple panels.

Please refer to the demo procedure to configure a successful camera and perform operations related to the camera panel.

> [TuyaCameraPanelSDK Demo](<https://github.com/TuyaInc/tuyasmart_camera_panel_android_sdk>)



### Set HomeId

Before jumping to the camera panel, you need to set the home Id where the camera device is located. Enter the corresponding panel page through the home Id and device Id

**Interface Description**

Set the homeId where the camera is currently located

 ```java
TuyaCameraPanelSDK.setCurrentHomeId(homeId);
 ```

 **Parameter Description**

| Parameter | Description                                                  |
| :-------- | :----------------------------------------------------------- |
| homeId    | the homeId where the device is located, which can be obtained through the  [TuyaSmartHomeSDK](https://tuyainc.github.io/tuyasmart_home_android_sdk_doc/zh-hans/)  - Home Management interface |

**Example Codes**

 ```java
TuyaCameraPanelSDK.setCurrentHomeId(homeId);
 ```

