# Module — `quadtree-graphic/gradle/wrapper` (LLD)

The `quadtree-graphic/gradle/wrapper` module carries a single configuration file—`gradle-wrapper.properties`—that pins the Gradle distribution to version 8.10.2 and specifies download URLs, local storage paths, and validation settings. Its sole purpose is bootstrapping: ensuring every developer and CI agent uses identical build tooling without manual installation. With zero fan-in and zero fan-out, this module sits entirely outside the runtime dependency graph; no production code depends on it, and it depends on no other modules in the codebase.

The public surface exposes only the properties file itself, readable by Gradle's wrapper script at build time. Because this is pure build-tool metadata—not application logic—it collaborates with nothing in the system and appears as an isolated leaf in both the module dependency lattice and the SCC analysis. The absence of Java sources or compiled artifacts means this module will never accrue cyclic dependencies or layering violations; it exists solely to anchor the build process to a known Gradle release.

For the full file listing and individual file purposes within this module, see the **Codebase Guide** entry for `quadtree-graphic/gradle/wrapper`.

_Domain hint: `Build tooling / Gradle wrapper configuration`_

## Responsibility

Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution to version 8.10.2 and defining download URLs, local storage locations, and validation settings so all developers and CI environments build with a consistent Gradle version. This module is isolated in the dependency graph and serves purely as build-tool bootstrapping metadata.

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
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Configures Gradle wrapper properties for the project, specifying the Gradle distribution version… | — |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__gradle__wrapper.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
