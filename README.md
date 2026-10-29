# Bastion for Android

**Documentation:** [pissmyran.github.io/bastion_android](https://pissmyran.github.io/bastion_android/)

Bastion is an SSH client. This repo holds the version for Android, built with Kotlin, Gradle and Apache MINA SSHD. The other platforms have their own repos: [Bastion for Apple](https://github.com/pissmyran/bastion_apple), [Bastion for Linux](https://github.com/pissmyran/bastion_linux), [Bastion for Windows](https://github.com/pissmyran/bastion_windows). The [Bastion hub](https://github.com/pissmyran/bastion) ties them together.

## Contents

| Path | Contents |
| --- | --- |
| `Android/app/` | The app: connection, SSH session and system information |
| `Android/` | The Gradle project with its own wrapper |
| `gradlew`, `gradle/` | Root wrapper that points to `Android/`, so tools run from the root find the project |

## Getting started

Test:

```bash
./gradlew test
```

Build a debug APK:

```bash
./gradlew assembleDebug
```

Run the commands from the repo root; the root `gradlew` forwards to `Android/`. The Android SDK must be installed and `ANDROID_HOME` set.

## More

- [The documentation](https://pissmyran.github.io/bastion_android/): getting started, architecture, operations, sync format and releases
- [SECURITY.md](SECURITY.md): report a vulnerability
- [CONTRIBUTING.md](CONTRIBUTING.md): contribute
