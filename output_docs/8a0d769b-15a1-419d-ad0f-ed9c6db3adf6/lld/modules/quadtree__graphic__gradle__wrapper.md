# Module — `quadtree-graphic/gradle/wrapper` (LLD)

The `quadtree-graphic/gradle/wrapper` module carries a single responsibility: pinning the build to Gradle 4.0 via its lone public surface artifact, `gradle-wrapper.properties`. This isolation is deliberate—fan-in and fan-out are both zero, meaning no other module in the codebase depends on or is depended upon by this wrapper configuration. It exists purely as build-tooling infrastructure, ensuring that developers and CI environments execute builds with a consistent Gradle distribution without requiring a local Gradle installation.

Because this module has no collaborators and no dependency edges, it represents a hermetically sealed leaf in the design. The public surface consists only of the properties file itself, which the Gradle wrapper mechanism reads at build time but which no runtime code references. This makes the module trivial to reason about during reviews: changes here affect build reproducibility and version policy, but never propagate through the module graph.

For the complete file inventory and any additional wrapper binaries (JAR, shell scripts) that may live alongside the properties file, consult the Codebase Guide entry for `quadtree-graphic/gradle/wrapper`.

_Domain hint: `build tooling / Gradle wrapper configuration`_

## Responsibility

Provides the Gradle Wrapper configuration for the quadtree-graphic project, pinning the build to Gradle 4.0 via `gradle-wrapper.properties` so that builds run consistently across environments without requiring a locally installed Gradle. This module is isolated in the dependency graph and acts purely as build-tooling configuration.

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
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Gradle wrapper configuration file that specifies the Gradle distribution to use (version 4.0), it… | — |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__gradle__wrapper.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
