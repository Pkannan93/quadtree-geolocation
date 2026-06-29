# Module — `quadtree-graphic/gradle/wrapper` (LLD)

The `quadtree-graphic/gradle/wrapper` module carries the responsibility of pinning the Gradle distribution version for the quadtree-graphic project, ensuring build reproducibility across developer machines and CI pipelines. Its single public surface—`gradle-wrapper.properties`—declares the Gradle 8.5 distribution URL and local cache location, removing any requirement for a pre-installed Gradle binary. This is a classic leaf module in the build-tooling layer: fan-in and fan-out are both zero, meaning no other modules depend on it and it depends on nothing within the codebase.

The isolation is intentional and appropriate for wrapper configuration, which sits outside the application's runtime dependency graph. The module contains no Java source and no collaborators, making it purely declarative infrastructure. Engineers modifying build behavior or upgrading Gradle will find this the sole entry point for distribution version control.

For the complete file manifest and any additional wrapper artifacts, consult the Codebase Guide entry for `quadtree-graphic/gradle/wrapper`.

_Domain hint: `build tooling / Gradle wrapper configuration`_

## Responsibility

Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution version (8.5) and specifying where the wrapper downloads and stores the Gradle distribution. This ensures all developers and CI environments build the project with a consistent Gradle version without requiring a pre-installed Gradle binary. The module is isolated with no inter-module dependencies.

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
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Configures the Gradle wrapper by specifying the Gradle distribution URL, version (8.5), and local… | — |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__gradle__wrapper.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
