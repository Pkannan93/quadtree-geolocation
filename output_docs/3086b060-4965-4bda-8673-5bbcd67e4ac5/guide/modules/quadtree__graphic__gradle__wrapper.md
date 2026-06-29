# Module — `quadtree-graphic/gradle/wrapper`

_Domain hint: `build tooling / Gradle wrapper configuration`_

## Responsibility

Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution version (8.5) and specifying where the wrapper downloads and stores the Gradle distribution. This ensures all developers and CI environments build the project with a consistent Gradle version without requiring a pre-installed Gradle binary. The module is isolated with no inter-module dependencies.

## Public surface

- `gradle-wrapper.properties`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Configures the Gradle wrapper by specifying the Gradle distribution URL, version (8.5), and local… | — |

---

See also: [Modules index](index.md) — every module in this run.
