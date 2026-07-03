# Module — `quadtree-graphic`

_Domain hint: `build tooling / project infrastructure (graphical quadtree application)`_

## Responsibility

Provides the Gradle build infrastructure for the `quadtree-graphic` project. Contains the Gradle wrapper scripts (`gradlew`, `gradlew.bat`) for Unix and Windows that bootstrap the Gradle build tool, along with `build.gradle` defining project metadata, Java source compatibility, repositories, and dependencies, and `settings.gradle` declaring the root project name. This module is isolated in the dependency graph — it does not import from or get imported by other code modules; it exists purely as build/tooling scaffolding.

## Public surface

- `gradlew`
- `gradlew.bat`
- `build.gradle`
- `settings.gradle`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/build.gradle` | Gradle build configuration file for the quadtree-graphic project. Defines project metadata (group… | — |
| `quadtree-graphic/gradlew` | This file is a Gradle wrapper shell script for Unix/Linux systems that bootstraps the Gradle buil… | — |
| `quadtree-graphic/gradlew.bat` | Windows batch script that launches the Gradle build system wrapper with proper Java configuration… | `gradlew.bat` |
| `quadtree-graphic/settings.gradle` | This is a Gradle settings file that configures the build settings for the 'quadtree-graphic' proj… | — |

---

See also: [Modules index](index.md) — every module in this run.
