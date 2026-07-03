# Module — `quadtree-graphic/gradle/wrapper` (LLD)

The `quadtree-graphic/gradle/wrapper` module holds the Gradle wrapper configuration that pins the Gradle distribution version to 8.5 and defines download/storage locations for the wrapper's distribution files. This responsibility ensures that builds are reproducible across developer environments without requiring a globally installed Gradle runtime. The single-file public surface—`gradle-wrapper.properties`—is a build-tool artifact rather than a source component, so the module exhibits zero fan-in and zero fan-out in the dependency graph: no other modules import from it, and it imports from no module.

This isolation is expected for build-tooling configuration. The Gradle wrapper is invoked by the build script infrastructure external to the module graph, so the absence of collaborators reflects its role as a side-channel configuration rather than a code dependency. Readers tracing import relationships or composition roots will not encounter this module in their navigation paths. For the full file listing—currently just the properties file—consult the Codebase Guide entry for `quadtree-graphic/gradle/wrapper`.

_Domain hint: `build tooling / Gradle wrapper configuration`_

## Responsibility

Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution version (8.5) and defining where the wrapper downloads and stores its distribution files. This ensures reproducible builds across developer machines without requiring a pre-installed Gradle. The module is isolated in the dependency graph, serving purely as build-tooling configuration.

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
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | This Gradle wrapper configuration file specifies the Gradle distribution to use (version 8.5) and… | — |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__gradle__wrapper.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
