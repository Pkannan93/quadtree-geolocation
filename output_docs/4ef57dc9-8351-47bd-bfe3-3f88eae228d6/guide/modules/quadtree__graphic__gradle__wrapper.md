# Module — `quadtree-graphic/gradle/wrapper`

_Domain hint: `build tooling / Gradle configuration`_

## Responsibility

Provides Gradle wrapper configuration for the quadtree-graphic project, specifying the Gradle distribution URL and version along with file system paths for the wrapper's base directory, zip storage, and JAR location. This enables reproducible Gradle builds across environments without requiring a pre-installed Gradle distribution.

## Public surface

- `distributionUrl`
- `distributionBase`
- `distributionPath`
- `zipStoreBase`
- `zipStorePath`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Gradle wrapper configuration file that specifies the Gradle distribution URL, version, and file s… | — |

---

See also: [Modules index](index.md) — every module in this run.
