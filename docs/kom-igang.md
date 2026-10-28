# Kom igång

## Förutsättningar

JDK (senaste LTS) och Android SDK med plattformen som `compileSdk` anger.

## Bygg och testa

Testa:

```bash
./gradlew test
```

Bygg en debug-APK:

```bash
./gradlew assembleDebug
```

Kommandona körs från repots rot; `gradlew` i roten skickar vidare till `Android/`. Android SDK måste finnas och `ANDROID_HOME` vara satt.

## Innehåll

| Plats | Innehåll |
| --- | --- |
| `Android/app/` | Appen: anslutning, SSH-session och systeminformation |
| `Android/` | Gradle-projektet med egen wrapper |
| `gradlew`, `gradle/` | Wrapper i roten som pekar på `Android/`, så att verktyg som körs från roten hittar projektet |
