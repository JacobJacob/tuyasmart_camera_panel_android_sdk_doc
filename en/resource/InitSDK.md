## Initialize the TuyaCameraPanelSDK 

Initialize TuyaCameraPanelSDK in Application

**Example Codes**

```java
public class TuyaSmartApp extends Application {
  @Override
  public void onCreate() {
    super.onCreate();

    // ... Confirm that appkey and appSecret exist
    TuyaWrapper.init(this);
    TuyaPanelSDK.init(this, "Appkey", "AppSecret");
    TuyaCameraPanelSDK.init(this);
    // ... 
  }
}
```

> Note: Appkey and AppSecret need to be configured in the AndroidManifest.xml file, or in the build environment, or written in the code.

