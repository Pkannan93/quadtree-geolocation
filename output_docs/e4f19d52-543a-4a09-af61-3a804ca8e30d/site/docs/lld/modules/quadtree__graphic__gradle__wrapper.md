# Module — `quadtree-graphic/gradle/wrapper` (LLD)

The `quadtree-graphic/gradle/wrapper` module holds the Gradle wrapper configuration that pins the project to a specific Gradle distribution, ensuring reproducible builds without requiring a global Gradle installation. Its sole public surface is `gradle-wrapper.properties`, which declares the distribution URL, version, and local cache paths. This is a classic leaf module: both fan-in and fan-out are zero, meaning no code in the system references it and it references nothing in return—its role is purely declarative for the build system runtime.

Because this module carries no collaborators and no dependent modules, it sits outside the compile-time dependency graph entirely. The isolation is intentional: wrapper configuration belongs to the build lifecycle, not application logic. Developers modifying the Gradle version or distribution URL will touch only this properties file, with no risk of rippling changes through Java or Kotlin source trees.

For the complete file inventory and any additional wrapper artifacts (like JAR or shell scripts), see the **Codebase Guide** entry for `quadtree-graphic/gradle/wrapper`.

_Domain hint: `build tooling / project infrastructure`_

## Responsibility

Provides Gradle wrapper configuration for the quadtree-graphic project, specifying the Gradle distribution URL, version, and local cache/distribution paths. This enables reproducible Gradle builds across environments without requiring developers to pre-install Gradle. The module is isolated with no inter-module dependencies.

## At a glance

| Dimension | Value |
|---|---|
| Files | 1 |
| Public surface | 1 symbol(s) |
| Collaborators | 0 |
| Fan-in | 0 module(s) |
| Fan-out | 0 module(s) |

## Public surface

- `gradle-wrapper.properties`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Configures the Gradle wrapper by specifying the Gradle distribution URL, version, and local cache… | — |


---

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__gradle__wrapper.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
