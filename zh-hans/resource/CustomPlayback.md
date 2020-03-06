## 自定义回放

若提供的回放面板不满足用户需求，用户可自行实现回放面板

**接口说明**

设置 PlaybackPanelListener 监听，跳转到自定义面板去实现回放

```java
TuyaCameraPanelSDK.setCustomPlaybackPanelListener(PlaybackPanelListener playbackListener);
```

 **参数说明**

| 参数             | 说明                                                         |
| :--------------- | :----------------------------------------------------------- |
| playbackListener | PlaybackPanelListener接口，设置此监听，可自定义回放面板；不设置则跳转到默认涂鸦摄像机回放面板 |

**示例代码**

```java
TuyaCameraPanelSDK.setCustomPlaybackPanelListener(new PlaybackPanelListener() {
    @Override
    public void onPlaybackPanelClick(String deviceId) {
        L.d(TAG, "回放面板 -自定义实现" + deviceId);
    }
});
```
