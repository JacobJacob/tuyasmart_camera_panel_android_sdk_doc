## Customize Album

User-defined local photo album

**Declaration**

Set AlbumPanelListener, customize the panel to achieve the current deviceId image preview, playback, cloud storage video playback, video information display,local storage path:

- Screenshot：Environment.getExternalStorageDirectory().absolutePath + "/Camera/" + deviceId + "/"；
- Record：Environment.getExternalStorageDirectory().absolutePath + "/Camera/Thumbnail/" + deviceId + "/"

```java
TuyaCameraPanelSDK.setCustomAlbumPanelListener(AlbumPanelListener albumPanelListener);
```

 **Parameters**

| Parameter          | Description                                                  |
| :----------------- | :----------------------------------------------------------- |
| albumPanelListener | AlbumPanelListener interface, set this listener to customize the album panel; if not set, skip to the default Tuya camera album panel |

**Example**

```java
TuyaCameraPanelSDK.setCustomAlbumPanelListener(new AlbumPanelListener() {
    @Override
    public void onAlbumPanelClick(String deviceId) {
        L.d(TAG, "customize album" + deviceId);
    }
});
```
