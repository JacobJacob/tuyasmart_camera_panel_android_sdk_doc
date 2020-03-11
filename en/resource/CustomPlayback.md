## Customize Playback

If the provided playback panel does not meet user needs, users can implement the playback panel by themselves,refer to [TuyaIPCCameraSDK - Playback](<https://tuyainc.github.io/tuyasmart_camera_android_sdk_doc/en/resource/PlaybackProcess.html>)

**Interface Description**

Set PlaybackPanelListener to jump to the custom panel to implement playback

```java
TuyaCameraPanelSDK.setCustomPlaybackPanelListener(PlaybackPanelListener playbackListener);
```

 **Parameter Description**

| Parameter        | Description                                                  |
| :--------------- | :----------------------------------------------------------- |
| playbackListener | PlaybackPanelListener interface, set this monitor to customize the playback panel; if not set, jump to the default Tuya camera playback panel |

**Example Codes**

```java
TuyaCameraPanelSDK.setCustomPlaybackPanelListener(new PlaybackPanelListener() {
    @Override
    public void onPlaybackPanelClick(String deviceId) {
        L.d(TAG, "Customize Playback " + deviceId);
    }
});
```
