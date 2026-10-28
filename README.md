# Bastion för Android

**Dokumentation:** [pissmyran.github.io/bastion_android](https://pissmyran.github.io/bastion_android/)

Bastion är en SSH-klient. Det här repot innehåller versionen för Android, byggd med Kotlin, Gradle och Apache MINA SSHD. Övriga plattformar har egna repon: [Bastion för Apple](https://github.com/pissmyran/bastion_apple), [Bastion för Linux](https://github.com/pissmyran/bastion_linux), [Bastion för Windows](https://github.com/pissmyran/bastion_windows).

## Innehåll

| Plats | Innehåll |
| --- | --- |
| `Android/app/` | Appen: anslutning, SSH-session och systeminformation |
| `Android/` | Gradle-projektet med egen wrapper |
| `gradlew`, `gradle/` | Wrapper i roten som pekar på `Android/`, så att verktyg som körs från roten hittar projektet |

## Kom igång

Testa:

```bash
./gradlew test
```

Bygg en debug-APK:

```bash
./gradlew assembleDebug
```

Kommandona körs från repots rot; `gradlew` i roten skickar vidare till `Android/`. Android SDK måste finnas och `ANDROID_HOME` vara satt.

## Mer

- [Dokumentationen](https://pissmyran.github.io/bastion_android/) – kom igång, arkitektur, drift, synkformat och release
- [SECURITY.md](SECURITY.md) – rapportera en sårbarhet
- [CONTRIBUTING.md](CONTRIBUTING.md) – bidra
