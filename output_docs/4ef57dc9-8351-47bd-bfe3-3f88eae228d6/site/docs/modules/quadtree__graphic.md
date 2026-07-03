# Module — `quadtree-graphic`

_Domain hint: `Build tooling / project scaffolding for a quadtree graphics application`_

## Responsibility

Provides the Gradle build infrastructure for the `quadtree-graphic` project, including the root project settings, Java 11 compilation configuration, JUnit 5 test dependency wiring, and the cross-platform Gradle wrapper scripts (`gradlew` for Unix, `gradlew.bat` for Windows) used to bootstrap builds. This module is an isolated build-tooling root with no runtime code dependencies on or from other modules in the graph.

## Public surface

- `gradlew`
- `gradlew.bat`
- `build.gradle`
- `settings.gradle`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/build.gradle` | This Gradle build configuration file sets up the quadtree-graphic project with Java plugin suppor… | — |
| `quadtree-graphic/gradlew` | Gradle wrapper shell script that bootstraps the Gradle build system by detecting the operating sy… | — |
| `quadtree-graphic/gradlew.bat` | Windows batch script that serves as a Gradle wrapper launcher. It configures the JVM environment,… | — |
| `quadtree-graphic/settings.gradle` | This is a Gradle settings file that defines the root project name for the quadtree-graphic build.… | — |

---

See also: [Modules index](index.md) — every module in this run.
