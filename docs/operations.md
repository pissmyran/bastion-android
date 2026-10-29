# Operations and verification

## Before every push

There are no build or test checks in CI. The tests below are the only test gate, so they run locally before every push:

Test:

```bash
./gradlew test
```

Build a debug APK:

```bash
./gradlew assembleDebug
```

## In CI

- **CodeQL** (GitHub's default setup) analyzes the code on every pull request and on `main`. Errors and serious security alerts block merging.
- **The documentation** is built strictly with Zensical when `docs/` or `zensical.toml` changes in a pull request.
- **The release** waits for the checks in `.github/release-required-checks`; see [Releases](release.md).

## The dependency graph

Keep the build script's `classpath` apart from the app's runtime dependencies. If GitHub flags a vulnerable build tool dependency that only exists transitively, declare the fixed version explicitly on the build script's classpath when Gradle and AGP support it, instead of filtering it out.

## Security rules

- Private keys, tokens and passwords never go into the repo, logs or test data.
- Values that reach a shell are quoted and preferably passed through `env:`.
- A dependency is updated in the manifest that actually owns it.
