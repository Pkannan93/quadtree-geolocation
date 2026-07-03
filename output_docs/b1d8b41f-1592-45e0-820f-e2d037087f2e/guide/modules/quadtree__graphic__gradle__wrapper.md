# Module — `quadtree-graphic/gradle/wrapper`

_Domain hint: `build tooling / Gradle wrapper configuration`_

## Responsibility

Provides the Gradle Wrapper configuration for the quadtree-graphic project, pinning the build to Gradle 4.0 via `gradle-wrapper.properties` so that builds run consistently across environments without requiring a locally installed Gradle. This module is isolated in the dependency graph and acts purely as build-tooling configuration.

## Public surface

- `gradle-wrapper.properties`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Gradle wrapper configuration file that specifies the Gradle distribution to use (version 4.0), it… | — |

---

See also: [Modules index](index.md) — every module in this run.
