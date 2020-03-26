## Customize feedback under the settings panel

Developers can customize feedback in Tuya Smart Camera Settings panel to implement feedback

**Declaration**

Set FeedbackListener to customize the panel to implement panel settings-feedback function

```java
TuyaCameraPanelSDK.setCustomFeedbackListener(FeedbackListener feedbackListener);
```

 **Parameters**

| Parameter        | Description                                                  |
| :--------------- | :----------------------------------------------------------- |
| feedbackListener | FeedbackListener interface. Set this listener to customize feedback. If you do not set this listener, this item will not be displayed |

**Example**

```java
TuyaCameraPanelSDK.setCustomFeedbackListener(new FeedbackListener() {
    @Override
    public void onFeedbackClick(String deviceId) {
        L.d(TAG, "Customize feedback");
    }
});
```

