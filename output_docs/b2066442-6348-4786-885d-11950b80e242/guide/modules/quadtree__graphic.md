# Module — `quadtree-graphic`

_Domain hint: `build tooling / project scaffolding`_

## Responsibility

Build infrastructure scaffolding for the `quadtree-graphic` Java project. Provides the Gradle build configuration (`build.gradle`, `settings.gradle`) declaring the Java plugin and JUnit 5 test dependency, plus the Gradle wrapper scripts (`gradlew`, `gradlew.bat`) that bootstrap Gradle on Unix and Windows without a pre-installed distribution. This module is isolated in the dependency graph and serves purely as the build entry point for the project.

## Public surface

- `gradlew`
- `gradlew.bat`
- `build.gradle`
- `settings.gradle`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/build.gradle` | Gradle build configuration file for the quadtree-graphic Java project. Sets up Java plugin, JUnit… | — |
| `quadtree-graphic/gradlew` | This file is a Gradle Wrapper shell script that bootstraps Gradle builds on Unix-like systems by… | — |
| `quadtree-graphic/gradlew.bat` | Provides a Windows batch script wrapper for executing Gradle builds on Windows systems. This scri… | `gradlew.bat` |
| `quadtree-graphic/settings.gradle` | Gradle settings file that configures the root project name for the quadtree-graphic application.… | — |

---

See also: [Modules index](index.md) — every module in this run.
