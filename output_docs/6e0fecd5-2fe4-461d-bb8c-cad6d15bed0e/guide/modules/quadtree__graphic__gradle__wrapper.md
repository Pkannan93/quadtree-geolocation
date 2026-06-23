# Module — `quadtree-graphic/gradle/wrapper`

_Domain hint: `build tooling / Gradle wrapper configuration`_

## Responsibility

Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution version (8.5) and defining where the wrapper downloads and stores its distribution files. This ensures reproducible builds across developer machines without requiring a pre-installed Gradle. The module is isolated in the dependency graph, serving purely as build-tooling configuration.

## Public surface

- `gradle-wrapper.properties`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | This Gradle wrapper configuration file specifies the Gradle distribution to use (version 8.5) and… | — |

---

See also: [Modules index](index.md) — every module in this run.
