# Module — `quadtree-graphic/gradle/wrapper` (LLD)

The `quadtree-graphic/gradle/wrapper` module holds the Gradle Wrapper configuration for the `quadtree-graphic` subproject, pinning the Gradle distribution version and defining download and cache locations to ensure reproducible builds without requiring a system-wide Gradle installation. This is a leaf module with zero fan-in and zero fan-out—it has no collaborators in the application dependency graph because it exists purely for the build toolchain's consumption. Its public surface consists solely of `gradle-wrapper.properties`, the standard configuration file that the Gradle wrapper script reads at build time.

Because this module sits outside the runtime dependency graph, it will never appear as a dependency or dependent of application code. Engineers modifying the Gradle version or adjusting distribution mirrors will interact with `gradle-wrapper.properties` directly, but the module otherwise remains invisible to code navigation and static analysis that traces compile-time or runtime relationships. For a complete listing of files in this module, consult the Codebase Guide entry for `quadtree-graphic/gradle/wrapper`.

_Domain hint: `Build tooling / project infrastructure`_

## Responsibility

Holds the Gradle Wrapper configuration that pins the Gradle distribution version and download/cache locations for the `quadtree-graphic` build, allowing the project to be built reproducibly without a pre-installed Gradle. This module is isolated in the dependency graph and is consumed only by the Gradle build tooling itself.

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
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Configuration file for Gradle wrapper that specifies the Gradle distribution URL, distribution ty… | — |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__gradle__wrapper.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
