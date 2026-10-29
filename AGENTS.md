# AGENTS.md – bastion_android

Bastion for Android: the SSH client for Android, built with Kotlin, Gradle and Apache MINA SSHD.

Read the shared rules at the start of every session: [GOVERNANCE.md](https://raw.githubusercontent.com/pissmyran/.github/main/GOVERNANCE.md) and [BASTION.md](https://raw.githubusercontent.com/pissmyran/.github/main/BASTION.md).

## Read first

1. [docs/architecture.md](docs/architecture.md): components and security boundaries.
2. [docs/operations.md](docs/operations.md): verification before pushing.
3. [docs/sync-format.md](docs/sync-format.md): when the host list or sync is involved.

## Commands

```bash
./gradlew test
./gradlew assembleDebug
```

Run from the repository root; the root `gradlew` forwards to `Android/`. The Android SDK must be installed and `ANDROID_HOME` set.

## Rules

- **Build scripts and runtime stay apart** in Gradle; see `docs/operations.md`.
- **Extra care:** host key verification and Gradle dependencies.
