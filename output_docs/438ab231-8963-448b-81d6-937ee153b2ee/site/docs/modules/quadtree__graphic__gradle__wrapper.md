# Module — `quadtree-graphic/gradle/wrapper`

_Domain hint: `Build tooling / project infrastructure`_

## Responsibility

Holds the Gradle Wrapper configuration that pins the Gradle distribution version and download/cache locations for the `quadtree-graphic` build, allowing the project to be built reproducibly without a pre-installed Gradle. This module is isolated in the dependency graph and is consumed only by the Gradle build tooling itself.

## Public surface

- `gradle-wrapper.properties`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Configuration file for Gradle wrapper that specifies the Gradle distribution URL, distribution ty… | — |

---

See also: [Modules index](index.md) — every module in this run.
