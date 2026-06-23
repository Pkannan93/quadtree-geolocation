# Module — `quadtree-graphic/gradle/wrapper` (LLD)

The `quadtree-graphic/gradle/wrapper` directory holds the Gradle wrapper configuration for the quadtree-graphic project, pinning a specific Gradle distribution version and download source to ensure reproducible builds across developer environments. With fan-in and fan-out both at zero, this module sits entirely outside the runtime dependency graph—it is pure build tooling infrastructure. Its single public surface artifact, `gradle-wrapper.properties`, declares the distribution URL and checksum, allowing the Gradle wrapper script to bootstrap the correct toolchain without requiring engineers to install Gradle manually.

Because this module has no collaborators and no dependents, it represents a leaf in the build-time infrastructure layer rather than the application layer. Changes here affect only the build environment: upgrading the Gradle version, switching mirror URLs, or adjusting wrapper verification settings. The isolation simplifies maintenance but also means that understanding this module requires context from the Gradle ecosystem rather than the application's domain logic.

For a complete file listing and any additional prose notes on this module's contents, see the **Codebase Guide** entry for `quadtree-graphic/gradle/wrapper`.

_Domain hint: `build tooling / Gradle configuration`_

## Responsibility

Configures the Gradle wrapper for the quadtree-graphic project, specifying which Gradle distribution version and download source to use so that builds run consistently across developer machines without requiring a pre-installed Gradle. This module is isolated and has no inter-module dependencies — it is purely build tooling configuration.

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
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | This is a Gradle wrapper properties configuration file that specifies the Gradle distribution ver… | — |


---

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__gradle__wrapper.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
