# Module — `quadtree-graphic/gradle/wrapper` (LLD)

The `quadtree-graphic/gradle/wrapper` module houses the Gradle wrapper configuration for the quadtree-graphic subproject, pinning a specific Gradle distribution version to guarantee reproducible builds without requiring a global Gradle installation. Its sole public surface is `gradle-wrapper.properties`, which declares the distribution URL and local cache path. With zero fan-in and zero fan-out, this module is a canonical leaf: no other module depends on it, and it imports nothing from the surrounding codebase.

This isolation is typical for build-tooling configuration — wrapper properties exist outside the runtime dependency graph and are consumed only by the Gradle daemon at build time. The absence of collaborators confirms that wrapper configuration remains orthogonal to application logic, reducing the risk of coupling build metadata to domain modules. The single-file composition keeps the wrapper footprint minimal and predictable.

For a complete file listing and deeper build-tooling context, see the Codebase Guide entry for `quadtree-graphic/gradle/wrapper`.

_Domain hint: `build tooling / Gradle wrapper configuration`_

## Responsibility

Provides Gradle wrapper configuration for the quadtree-graphic subproject, declaring which Gradle distribution version to download and where to cache it locally so the project can be built reproducibly without a pre-installed Gradle. This module is isolated with no inter-module dependencies.

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
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Configures the Gradle wrapper for the quadtree-graphic project, specifying the Gradle distributio… | — |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__gradle__wrapper.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
