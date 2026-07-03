# Module — `quadtree-graphic/gradle/wrapper` (LLD)

The `quadtree-graphic/gradle/wrapper` module is a zero-fan-in, zero-fan-out leaf responsible for housing the Gradle wrapper properties that lock the project to a specific Gradle distribution. Its public surface exposes five configuration keys—`distributionUrl`, `distributionBase`, `distributionPath`, `zipStoreBase`, and `zipStorePath`—which collectively ensure that any developer or CI pipeline can bootstrap a build without a system-wide Gradle installation. Because this module declares no collaborators and is depended upon by no other module in the codebase, it sits entirely outside the directed dependency graph; its influence is felt only at build-time when the Gradle wrapper script consumes `gradle-wrapper.properties`.

The single-file nature and absence of code dependencies make this module trivial to reason about, though its isolation also means reviewers should verify that the `distributionUrl` points to a vetted, checksum-validated archive and that the wrapper JAR (not tracked here) remains in sync with the declared version. For a complete file listing and any supplementary build artifacts, consult the Codebase Guide entry for `quadtree-graphic/gradle/wrapper`.

_Domain hint: `build tooling / Gradle configuration`_

## Responsibility

Provides Gradle wrapper configuration for the quadtree-graphic project, specifying the Gradle distribution URL and version along with file system paths for the wrapper's base directory, zip storage, and JAR location. This enables reproducible Gradle builds across environments without requiring a pre-installed Gradle distribution.

## At a glance

| Dimension | Value |
|---|---|
| Files | 1 |
| Public surface | 5 symbol(s) |
| Collaborators | 0 |
| Fan-in | 0 module(s) |
| Fan-out | 0 module(s) |

## Public surface

- `distributionUrl`
- `distributionBase`
- `distributionPath`
- `zipStoreBase`
- `zipStorePath`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties` | Gradle wrapper configuration file that specifies the Gradle distribution URL, version, and file s… | — |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__gradle__wrapper.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
