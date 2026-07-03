# Module — `quadtree-graphic/gradle/wrapper`

_Domain hint: `build tooling / Gradle wrapper configuration`_

## Responsibility

Provides the Gradle wrapper configuration for the `quadtree-graphic` project, specifying which Gradle distribution version to download, where to fetch it from, and where to cache the distribution and wrapper files locally. This module is isolated in the dependency graph and serves purely as build tooling configuration consumed by the Gradle wrapper scripts.

## Public surface

- `gradle-wrapper.properties`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Configures the Gradle wrapper for the project, specifying the Gradle distribution type, download… | — |

---

See also: [Modules index](index.md) — every module in this run.
