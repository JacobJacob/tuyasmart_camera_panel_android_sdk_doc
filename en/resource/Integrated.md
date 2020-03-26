## Integrated SDK

### 1. Create project

Build your project in Android Studio

### 2. Configure build.gradle in the root directory

Add the addresses of dependencies to be integrated in the build.gradle file in the root directory.

```java
allprojects {
    repositories {
        //***** required start ****//
        maven { url "https://maven-other.tuya.com/repository/maven-releases/"}
      	maven { url "https://maven-other.tuya.com/repository/maven-snapshots/" }
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
      	maven { url "https://maven-other.tuya.com/repository/maven-snapshots/" }
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

### 3.  Configure build.gradle in the module directory

In the module's build.gradle file, add the dependencies and some configurations in the integration preparation.

```java   
apply plugin: 'com.android.application'
apply plugin: 'tymodule-config'

android {
    //... 
    defaultConfig {
        //...
        multiDexEnabled true
        ndk {
            abiFilters "armeabi-v7a", "arm64-v8a"
        }
    }
    
    //***** start ****//
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
    //***** end ****//
}

dependencies {
    //***** Tuya IPC Camera Panel SDK ****//
    implementation 'com.tuya.smart:tuyasmart-camera-panel-sdk:1.0.1'
    //TuyaSmartSdk
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
    //*****  Tuya IPC Camera Panel SDK ****//

    //Third-party component dependencies
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
    //***** end ****//

    //...
}
```

### 4. Configure AndroidManifest.xml

Configure appkey and appSecret in AndroidManifest.xml file, configure corresponding permissions, etc.

```java
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
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
            android:value="Your Appkey" />
        <meta-data
            android:name="TUYA_SMART_SECRET"
            android:value="Your AppSecret" />
       <!--   ...	 -->
    </application>
```

### 5. Configure proguard-rules.pro

Configure in the proguard-rules.pro file

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

### 