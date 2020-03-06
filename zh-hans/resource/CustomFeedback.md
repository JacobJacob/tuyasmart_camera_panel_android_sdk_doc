## 设置面板 - 自定义意见反馈

用户在涂鸦智能摄像机设置面板内去自定义实现意见反馈

**接口说明**

设置 FeedbackListener 监听，自定义面板去实现面板设置-意见反馈功能

```java
TuyaCameraPanelSDK.setCustomFeedbackListener(FeedbackListener feedbackListener);
```

 **参数说明**

| 参数             | 说明                                                         |
| :--------------- | :----------------------------------------------------------- |
| feedbackListener | FeedbackListener接口，设置此监听，可自定义实现 意见反馈，不设置该监听则面板上将不显示此项 |

**示例代码**

```java
TuyaCameraPanelSDK.setCustomFeedbackListener(new FeedbackListener() {
    @Override
    public void onFeedbackClick(String deviceId) {
        L.d(TAG, "意见反馈 -自定义实现");
    }
});
```

