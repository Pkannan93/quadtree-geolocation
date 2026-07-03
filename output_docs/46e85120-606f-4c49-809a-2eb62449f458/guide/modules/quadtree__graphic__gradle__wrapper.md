# Module — `quadtree-graphic/gradle/wrapper`

_Domain hint: `Build tooling / Gradle wrapper configuration`_

## Responsibility

Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution to version 8.10.2 and defining download URLs, local storage locations, and validation settings so all developers and CI environments build with a consistent Gradle version. This module is isolated in the dependency graph and serves purely as build-tool bootstrapping metadata.

## Public surface

- `gradle-wrapper.properties`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Configures Gradle wrapper properties for the project, specifying the Gradle distribution version… | — |

---

See also: [Modules index](index.md) — every module in this run.
