# SpeedView

[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-SpeedView-blue.svg?style=true)](https://android-arsenal.com/details/1/4169)
[![Gitter](https://badges.gitter.im/AnasTr/SpeedView.svg)](https://gitter.im/AnasTr/SpeedView?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)
[![API](https://img.shields.io/badge/API-+11-red.svg?style=flat)](#)
[![Bintray](https://img.shields.io/bintray/v/anastr/maven/SpeedView.svg?color=green)](https://bintray.com/anastr/maven/SpeedView)
[![Twitter](https://img.shields.io/badge/Twitter-@AnasAltairDent-blue.svg?style=flat)](http://twitter.com/AnasAltairDent)

# Download

this library required **jcenter** and **kotlin version 1.3.61** 

first add kotlin to your project, in `build.gradle` **project level**:

```gradle
buildscript {
    ext.kotlin_version = '1.3.61'
    dependencies {
        ...
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
    }
}
...
allprojects {
    repositories {
        ...
        jcenter()
    }
}
```

add this line to `build.gradle` **app module level**:

```gradle
apply plugin: 'kotlin-android'
...
dependencies {
	implementation 'com.github.anastr:speedviewlib:1.5.2'
}

```

for **maven**

```maven
<dependency>
  <groupId>com.github.anastr</groupId>
  <artifactId>speedviewlib</artifactId>
  <version>1.5.2</version>
  <type>pom</type>
</dependency>
```
**[Get Starting]
# Simple Usage
choose one of Speedometers, gauges and add it to your `Layout.xml`, here we use **SpeedView**.<br>
```xml

<com.github.anastr.speedviewlib.SpeedView
        android:id="@+id/speedView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

```

for all speedometers and gauges, this simple method to smoothly change speed:
```java
SpeedView speedometer = findViewById(R.id.speedView)

// move to 50 Km/s
speedometer.speedTo(50)
```

by default, the speed change Duration between last speed and new speed is `2000 ms`.<br>
you can use other Duration by method :
```java
// move to 50 Km/s with Duration = 4 sec
speedometer.speedTo(50, 4000)
```

automatically indicator move around current speed to add some reality to speedometer because of [Tremble], you can stop it by `app:sv_withTremble="false"` Attribute or call `speedometer.withTremble = false` method in the code.
<br>
<img src="/images/usage/StartEndDegree.png" width="40%" />
<img src="/images/usage/WorkWithNote.gif" width="35%" />

