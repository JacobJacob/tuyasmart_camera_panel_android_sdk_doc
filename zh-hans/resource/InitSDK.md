## TuyaCameraPanelSDK 初始化

在 Application 中初始化 TuyaCameraPanelSDK

**示例代码**

```java
public class TuyaSmartApp extends Application {
  @Override
  public void onCreate() {
    super.onCreate();

    // ... 确认 appkey ，appSecret存在
    TuyaWrapper.init(this);
    TuyaPanelSDK.init(this, "应用Appkey", "应用密钥AppSecret");
    TuyaCameraPanelSDK.init(this);
    // ... 其他
  }
}
```

> 注意事项 Appkey 和 AppSecret 需要配置 AndroidManifest.xml 文件里，或者在 build 环境里配置，也可以在代码里写入。

