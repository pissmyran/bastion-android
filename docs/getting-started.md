# Getting started

## Prerequisites

A JDK (latest LTS) and the Android SDK with the platform that `compileSdk` names.

## Build and test

Test:

```bash
./gradlew test
```

Build a debug APK:

```bash
./gradlew assembleDebug
```

Run the commands from the repo root; the root `gradlew` forwards to `Android/`. The Android SDK must be installed and `ANDROID_HOME` set.

## Contents

| Path | Contents |
| --- | --- |
| `Android/app/` | The app: connection, SSH session and system information |
| `Android/` | The Gradle project with its own wrapper |
| `gradlew`, `gradle/` | Root wrapper that points to `Android/`, so tools run from the root find the project |
