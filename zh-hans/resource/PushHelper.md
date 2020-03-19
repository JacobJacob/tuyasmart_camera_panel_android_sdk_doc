##  消息推送辅助协议

在APP进程活着的情况下，为提高推送消息的到达及时性和成功率，涂鸦智能摄像机开放了消息推送辅助协议。

- 用户自行实现接入推送渠道，可参考  [涂鸦全屋智能 SDK 系统推送消息](https://tuyainc.github.io/tuyasmart_home_android_sdk_doc/zh-hans/resource/MessagePush.html)

- 注册涂鸦推送消息监听，获取回调上来的推送消息，进行后续处理


消息体格式定义示例

```json
{
"a": "view",
"c": "action",
"cc": "低功耗智能摄像机 ,someone is ringing the bell.",
"ct": "fcm You have a visitor",
"devId": "6cfaf335a8d6e752e0wrpy",
"msgId": "4da4dcf61573555995",
"p": {
"media": 13
},
"specialChannel": false,
"ts": "1573555995000",
"type": "doorbell"
}
```



### 注册和注销监听

在账号登录成功后注册,在账号退出时进行注销

**接口说明**

涂鸦推送辅助协议需在账号登陆成功后注册监听，在账号退出时进行注销

```java
//注册涂鸦推送消息监听
TuyaHomeSdk.getCameraInstance().registerCameraPushListener(ITuyaGetBeanCallback<CameraPushDataBean> callback)
  
//注销涂鸦推送消息监听
TuyaHomeSdk.getCameraInstance().unRegisterCameraPushListener(ITuyaGetBeanCallback<CameraPushDataBean> callback)；
```

 **参数说明**

| 参数     | 说明                                                         |
| :------- | :----------------------------------------------------------- |
| callback | ITuyaGetBeanCallback 接口，监听回调推送消息，CameraPushDataBean 为推送消息封装 |

**CameraPushDataBean 数据模型**

| 字段      | 类型    | 描述       |
| :-------- | :------ | :--------- |
| devId     | String  | 设备id     |
| timestamp | Integer | 消息时间戳 |
| etype     | String  | 消息类型   |
| edata     | String  | 消息id     |

**示例代码**

```java
private ITuyaHomeCamera homeCamera;
private static ITuyaGetBeanCallback<CameraPushDataBean> mTuyaGetBeanCallback = new ITuyaGetBeanCallback<CameraPushDataBean>() {
    @Override
    public void onResult(CameraPushDataBean o) {
        L.d(TAG, "onMqtt_43_Result on callback");
        L.d(TAG, "消息时间戳：timestamp=" + o.getTimestamp());
        L.d(TAG, "设备id：devid=" + o.getDevId());
        L.d(TAG, "消息id：msgid=" + o.getEdata());
        L.d(TAG, "消息类型：etype=" + o.getEtype());
    }
};

/**
 * 在账号登陆成功之后注册
 */
public void registerCameraPushListener() {
    homeCamera = TuyaHomeSdk.getCameraInstance();
    if (homeCamera != null) {
        homeCamera.registerCameraPushListener(mTuyaGetBeanCallback);
    }
}

/**
 * 在账号注销之后进行反注册
 */
public void unRegisterCameraPushListener() {
    if (homeCamera != null) {
        homeCamera.unRegisterCameraPushListener(mTuyaGetBeanCallback);
    }
}
```

> **注意**: 
>
> 1. 当app进程被杀死的时候，该监听无效。在app登录成功之后，注册监听；app退出登录，取消监听
>
> 2. 避免重复的推送消息（用户自有渠道推送、涂鸦辅助协议产生），可通过消息id，消息类型，消息到达时间来进行过滤