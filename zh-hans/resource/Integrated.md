## 集成 SDK
1. 创建工程

   在 Android Studio 中建立你的工程

2. 根目录 build.gradle 配置

  在根目录 build.gradle 文件里添加需要集成的 dependencies 依赖库地址。

  ```java
  allprojects {
      repositories {
          //***** required start ****//
          maven { url "https://maven-other.tuya.com/repository/maven-releases/"}
          maven { url 'https://jitpack.io' }
          //***** required end ****//
          google()
          jcenter()
          mavenCentral()
      }
  }

  buildscript {
      repositories {
          maven {url "https://maven-other.tuya.com/repository/maven-releases/"}
          maven { url "https://jitpack.io" }
          mavenLocal()
          mavenCentral()
          google()
          jcenter()
      }
      dependencies {
          classpath 'com.android.tools.build:gradle:3.5.0'
          classpath 'com.antfortune.freeline:gradle:0.8.6'
          classpath "com.google.protobuf:protobuf-gradle-plugin:0.8.6"
          classpath 'org.apache.httpcomponents:httpclient:4.4.1'
          classpath 'com.tuya.android.module:tymodule-config:0.4.0'
      }
  }
  ```

3. 模块 build.gradle 配置

  在模块 build.gradle 文件里添加集成准备中下载的 dependencies 依赖及一些配置。

  ```java   
  apply plugin: 'com.android.application'
  apply plugin: 'tymodule-config'

  android {
      //... 其他默认配置
      defaultConfig {
          //...其他默认配置
          multiDexEnabled true
          ndk {
              abiFilters "armeabi-v7a", "arm64-v8a"
          }
      }

      //***** 强制配置 开始 ****//
      compileOptions {
          sourceCompatibility 1.8
          targetCompatibility 1.8
      }

      packagingOptions {
          pickFirst 'lib/*/libc++_shared.so'
          pickFirst 'lib/*/libgnustl_shared.so'
      }

      lintOptions {
          abortOnError false
          disable 'InvalidPackage'
      }
      //***** 强制配置 结束 ****//
  }

  dependencies {
      //***** 涂鸦摄像头面板SDK模块 必须依赖 开始 ****//
      implementation 'com.tuya.smart:tuyasmart-camera-panel-sdk:1.0.1'
      //涂鸦公版组件依赖
      implementation 'com.tuya.smart:tuyasmart:3.13.0'
      implementation "com.tuya.smart:tuyasmart-TuyaRNApi:5.22.54-open"
      implementation 'com.tuya.smart:panel-sdk:0.4.0'
      implementation 'com.tuya.smart:tuyasmart-video:3.12.6r125'
      implementation 'com.tuya.smart:tuyasmart-imagepipeline-okhttp3:0.0.1'
      implementation 'com.tuya.android.module:tymodule-annotation:0.0.7.2'
      implementation 'com.tuya.smart:tuyasmart-webcontainer:3.12.6r125-h1'
      implementation 'com.tuya.smart:tuyasmart-appshell:3.10.0'
      implementation 'com.tuya.smart:tuyasmart-rpc:3.12.0r123'
      implementation 'com.tuya.smart:tuyasmart-security:1.0.0'
      implementation 'com.tuya.smart:tuyasmart-wkvideoplayer:1.0.0'
      //*****  涂鸦摄像头面板SDK模块 必须依赖 结束 ****//

      //第三方组件依赖
      implementation 'com.weigan:loopView:0.1.1'
      implementation 'com.facebook.infer.annotation:infer-annotation:0.11.2'
      implementation 'com.facebook.soloader:soloader:0.8.0'
      implementation 'com.facebook.fresco:fresco:1.3.0'
      implementation 'com.facebook.fresco:animated-gif:1.3.0'
      implementation "com.facebook.fresco:imagepipeline-okhttp3:1.3.0"
      implementation 'com.squareup.okhttp3:okhttp-urlconnection:3.2.0'
      implementation 'javax.inject:javax.inject:1'
      implementation 'com.alibaba:fastjson:1.1.67.android'
      implementation 'com.facebook.react:react-native:0.51.1.11'
      implementation 'com.airbnb.android:lottie:2.7.0'
      implementation 'org.apache.commons:commons-compress:1.9'
      implementation 'com.kyleduo.switchbutton:library:1.4.2'
      implementation 'com.github.PhilJay:MPAndroidChart:v3.0.3'
      implementation 'org.eclipse.paho:org.eclipse.paho.client.mqttv3:1.2.0'
      implementation 'io.reactivex.rxjava2:rxandroid:2.0.1'
      implementation 'io.reactivex.rxjava2:rxjava:2.1.7'
      implementation 'com.hannesdorfmann:adapterdelegates3:3.1.0'
      implementation 'com.android.support.constraint:constraint-layout:1.1.3'
      implementation 'com.android.support:multidex:1.0.3'
      implementation "com.android.support:appcompat-v7:28.0.0"
      implementation "com.android.support:cardview-v7:28.0.0"
      implementation "com.android.support:recyclerview-v7:28.0.0"
      implementation "com.android.support:support-annotations:28.0.0"
      implementation "com.android.support:support-compat:28.0.0"
      implementation "com.android.support:support-fragment:28.0.0"
      implementation "com.android.support:design:28.0.0"
      implementation "com.android.support:support-v4:28.0.0"
      //***** 必须依赖模块 结束 ****//

      //... 其他默认配置
  }
  ```

4. AndroidManifest.xml 配置

  在 AndroidManifest.xml 文件里配置 appkey 和 appSecret ，在配置相应的权限等

  ```java
      <!-- sdcard 权限-->
      <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
      <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
      <!-- 网络 权限-->
      <uses-permission android:name="android.permission.INTERNET" />
      <uses-permission android:name="android.permission.CHANGE_NETWORK_STATE" />
      <uses-permission android:name="android.permission.CHANGE_WIFI_STATE" />
      <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
      <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
      <uses-permission android:name="android.permission.RECORD_AUDIO" />
      <uses-permission android:name="android.permission.MODIFY_AUDIO_SETTINGS" />
      <uses-permission
          android:name="android.permission.ACCESS_FINE_LOCATION"
          android:required="false" />
      <uses-permission
          android:name="android.permission.WAKE_LOCK"
          android:required="false" />
      <uses-permission
          android:name="android.permission.CHANGE_WIFI_MULTICAST_STATE"
          android:required="false" />
      <uses-permission android:name="android.permission.VIBRATE" />

      <application >

          <meta-data
              android:name="TUYA_SMART_APPKEY"
              android:value="用户申请的应用Appkey" />
          <meta-data
              android:name="TUYA_SMART_SECRET"
              android:value="用户申请的应用密钥AppSecret" />

         <!--    ... -->
      </application>
  ```

5. 混淆配置

  在 proguard-rules.pro 文件配置相应混淆配置

  ```java
      //...
      #fastJson
      -keep class com.alibaba.fastjson.**{*;}
      -dontwarn com.alibaba.fastjson.**

      #mqtt
      -keep class org.eclipse.paho.client.mqttv3.** { *; }
      -dontwarn org.eclipse.paho.client.mqttv3.**

      -dontwarn okio.**
      -dontwarn rx.**
      -dontwarn javax.annotation.**
      -keep class com.squareup.okhttp.** { *; }
      -keep interface com.squareup.okhttp.** { *; }
      -keep class okio.** { *; }
      -dontwarn com.squareup.okhttp.**

      -keep class com.tuya.**{*;}
      -dontwarn com.tuya.**
  ```
