## TuyaCameraPanelSDK 面板调用

TuyaCameraPanelSDK 是涂鸦智能摄像机各面板的调用对外暴露的接口，包含多个面板的跳转及自定义实现。

参考 demo 流程，配置成功摄像头，进行摄像头面板相关操作 

> [TuyaCameraPanelSDK Demo](<https://github.com/TuyaInc/tuyasmart_camera_panel_android_sdk>)



### 设置家庭ID

跳转到摄像机面板前，需设置摄像机设备所在的家庭 Id，通过家庭 Id 和设备 Id 进入相应的面板页面

**接口说明**

设置摄像头当前所在的家庭ID

 ```java
TuyaCameraPanelSDK.setCurrentHomeId(homeId);
 ```

 **参数说明**

| 参数   | 说明                                                         |
| :----- | :----------------------------------------------------------- |
| homeId | 设备所在的家庭ID，可通过 [涂鸦全屋智能 SDK](https://tuyainc.github.io/tuyasmart_home_android_sdk_doc/zh-hans/) 家庭管理对应的接口获取 |

**示例代码**

 ```java
TuyaCameraPanelSDK.setCurrentHomeId(homeId);
 ```

