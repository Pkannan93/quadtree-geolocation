# Module — `quadtree-graphic/gradle/wrapper`

_Domain hint: `build tooling / Gradle wrapper configuration`_

## Responsibility

Provides Gradle wrapper configuration for the quadtree-graphic subproject, declaring which Gradle distribution version to download and where to cache it locally so the project can be built reproducibly without a pre-installed Gradle. This module is isolated with no inter-module dependencies.

## Public surface

- `gradle-wrapper.properties`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Configures the Gradle wrapper for the quadtree-graphic project, specifying the Gradle distributio… | — |

---

See also: [Modules index](index.md) — every module in this run.
