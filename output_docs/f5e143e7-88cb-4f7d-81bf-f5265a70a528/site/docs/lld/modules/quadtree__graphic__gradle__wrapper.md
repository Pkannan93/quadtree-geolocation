# Module — `quadtree-graphic/gradle/wrapper` (LLD)

The `quadtree-graphic/gradle/wrapper` module lives at the perimeter of the build system, holding a single configuration artifact—`gradle-wrapper.properties`—that pins the Gradle distribution version and download location for the `quadtree-graphic` project. With zero fan-in and zero fan-out, this is a pure leaf module: no other code depends on it, and it imports nothing from the application graph. Its sole responsibility is to anchor the Gradle wrapper scripts to a specific distribution URL and local cache path, ensuring repeatable builds without requiring engineers to pre-install Gradle.

This isolation is typical for wrapper configuration, but it means the module offers no programmatic surface to the rest of the system—`gradle-wrapper.properties` is consumed by build tooling outside the Java compilation phase, not by runtime classes or even other Gradle build scripts within the module tree. The lack of collaborators confirms that this directory exists strictly for toolchain bootstrapping, orthogonal to the application's logical architecture.

For the complete file manifest and any future JAR or checksum additions, see the **Codebase Guide** entry for `quadtree-graphic/gradle/wrapper`.

_Domain hint: `build tooling / Gradle wrapper configuration`_

## Responsibility

Provides the Gradle wrapper configuration for the `quadtree-graphic` project, specifying which Gradle distribution version to download, where to fetch it from, and where to cache the distribution and wrapper files locally. This module is isolated in the dependency graph and serves purely as build tooling configuration consumed by the Gradle wrapper scripts.

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
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Configures the Gradle wrapper for the project, specifying the Gradle distribution type, download… | — |


---

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__gradle__wrapper.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
