## Customize Theme

Themes include two types: black and white, support the settings panel and local album panel of Tuya Smart Camera

**Interface Description**

Users can set the theme through TuyaCameraPanelSDK.setTheme () method

```java
// themeId 1：black，2：white
TuyaCameraPanelSDK.setTheme(themeId)；
```

 **Parameter Description**

| Parameter | Description          |
| :-------- | :------------------- |
| themeId   | int: 1,black;2,white |

**Example Codes**

```java
TuyaCameraPanelSDK.setTheme(1)；
```

> Only support settings / local album panel

