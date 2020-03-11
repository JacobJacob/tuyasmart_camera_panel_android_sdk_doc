## 自定义主题

主题包括黑色和白色2种，支持涂鸦智能摄像头的设置面板和本地相册面板

**接口说明**

用户可通过TuyaCameraPanelSDK.setTheme()方法来设置主题

```java
// themeId 1：黑色主题，2：白色主题
TuyaCameraPanelSDK.setTheme(themeId)；
```

 **参数说明**

| 参数    | 说明                            |
| :------ | :------------------------------ |
| themeId | int型：1，黑色主题；2，白色主题 |

**示例代码**

```java
TuyaCameraPanelSDK.setTheme(1)；
```

> 仅支持设置/本地相册面板
