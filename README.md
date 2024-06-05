## Overview

This project contains a single conventions plugin that applies a subset of the configuration recommended in the Android Instrumented Test Support for Gradle Enterprise (Beta) document. Since the conventions plugin uses AGP classes, it must include AGP as an implementation dependency. But, when included, this dependency fails to resolve with the following error:

```
> Could not find com.android.tools.build:gradle:8.4.0.
     Searched in the following locations:
       - https://plugins.gradle.org/m2/com/android/tools/build/gradle/8.4.0/gradle-8.4.0.pom
     Required by:
         project : > project :build-logic
```

It searches for the dependency in https://plugins.gradle.org, even though the only two defined repositories are `google()` and `mavenCentral()`.

## Reproducing the Issue

Run `./gradlew help`
