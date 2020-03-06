## 自定义相册

用户自定义实现本地相册

**接口说明**

设置 AlbumPanelListener 监听，自定义面板去实现当前deviceId在预览，回放，云存储视频播放中保存的图片，视频信息展示，本地路径为：

- 截图路径：Environment.getExternalStorageDirectory().absolutePath + "/Camera/" + deviceId + "/"；
- 录制路径：Environment.getExternalStorageDirectory().absolutePath + "/Camera/Thumbnail/" + deviceId + "/"

```java
TuyaCameraPanelSDK.setCustomAlbumPanelListener(AlbumPanelListener albumPanelListener);
```

 **参数说明**

| 参数               | 说明                                                         |
| :----------------- | :----------------------------------------------------------- |
| albumPanelListener | AlbumPanelListener接口，设置此监听，可自定义相册面板；不设置则跳转到默认涂鸦摄像机相册面板 |

**示例代码**

```java
TuyaCameraPanelSDK.setCustomAlbumPanelListener(new AlbumPanelListener() {
    @Override
    public void onAlbumPanelClick(String deviceId) {
        L.d(TAG, "相册面板 -自定义实现" + deviceId);
    }
});
```
