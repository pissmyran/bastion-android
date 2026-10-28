# Drift och verifiering

## Före varje push

Det finns inga bygg- eller testkontroller i CI. Testerna nedan är den enda testgrinden, så de körs lokalt före varje push:

Testa:

```bash
./gradlew test
```

Bygg en debug-APK:

```bash
./gradlew assembleDebug
```

## I CI

- **CodeQL** (GitHubs standardinställning) analyserar koden på varje pull request och på `main`. Fel och allvarliga säkerhetslarm stoppar merge.
- **Dokumentationen** byggs strikt med Zensical när `docs/` eller `zensical.toml` ändras i en pull request.
- **Releasen** väntar på kontrollerna i `.github/release-required-checks`; se [Release](release.md).

## Beroendegrafen

Skilj mellan byggskriptets `classpath` och appens runtime-beroenden. Flaggar GitHub ett sårbart byggverktygsberoende som bara finns transitivt, deklarera den rättade versionen uttryckligen på byggskriptets classpath om Gradle och AGP stöder det, i stället för att filtrera bort det.

## Säkerhetsregler

- Privata nycklar, tokens och lösenord läggs aldrig i repot, i loggar eller i testdata.
- Värden som når ett skal citeras och skickas helst via `env:`.
- Ett beroende uppdateras i det manifest som faktiskt äger det.
