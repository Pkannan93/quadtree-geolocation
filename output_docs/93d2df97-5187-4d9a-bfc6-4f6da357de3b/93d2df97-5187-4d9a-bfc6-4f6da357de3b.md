# Geospatial indexing and visualization (quadtree-based nearest-neighbor search) Documentation

_Source: `https://github.com/Pkannan93/quadtree-geolocation.git`
 @ `a1b444ae134e`
_

## Overview
**Purpose.** This repository implements an interactive 2D visualization of a quadtree spatial index for geographic nearest-neighbor search. The core spatial indexing logic lives in `quadtree-graphic/src/main/java/src/quadtree/core` (with `QuadTree`, `QuadTreeNode`, `Neighbour`, and `QuadTreeConstants`), which is wrapped for rendering by `quadtree-graphic/src/main/java/src/quadtree` (`DrawableQuadTree`, `DrawableQuadTreeNode`) and presented through a Swing/AWT application shell in `quadtree-graphic/src/main/java/src` (`Main`, `CanvasPanel`, `MainScreen`). Build and tooling are handled by Gradle wrapper configuration in `quadtree-graphic` and `quadtree-graphic/gradle/wrapper`. Although the supplied graph reports no edges (modules appear as isolated nodes in a single layer), the source-level intent is a clear layering from core data structure → drawable adapters → UI shell → entry point.

**Architecture style.** layered desktop application (core data-structure library wrapped by drawable adapters and a Swing UI shell)
**Primary domain.** Geospatial indexing and visualization (quadtree-based nearest-neighbor search)

**Key capabilities:**
- Quadtree-based spatial indexing with insertion, removal, and range/proximity queries over geographic coordinates
- Geographic distance-to-degree conversion and configurable tuning via QuadTreeConstants
- Graphical rendering of quadtree nodes, boundaries, and neighbor points via Drawable wrappers
- Interactive Swing/AWT canvas with pan, zoom, and mouse-driven nearest-neighbor search
- Reproducible Gradle-based build for a Java 1.8 application with JUnit testing

> _Evidence_: `.gitignore:1`, `quadtree-graphic/build.gradle:1`, `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties:1` (confidence 0.80)

## Business Capabilities
### Context: `build tooling / gradle wrapper configuration`
- **wrapper** — Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution version (8.5) and defining where the wrapper downloads and stores its distribution files. This ensures reproducible builds across developer machines without requiring a pre-installed Gradle. The module is isolated in the dependency graph, serving purely as build-tooling configuration.

### Context: `build tooling / project scaffolding for a quadtree graphics application`
- **quadtree-graphic** — Provides Gradle build infrastructure for the quadtree-graphic Java project, including build configuration (`build.gradle`), project settings (`settings.gradle`), and cross-platform Gradle wrapper scripts (`gradlew`, `gradlew.bat`) for Unix and Windows environments. Targets Java 1.8 with JUnit for testing. This module appears isolated in the dependency graph, suggesting it scaffolds a standalone build environment for a quadtree-based graphical application.

### Context: `geolocation / spatial data structures (quadtree)`
- **.** — This top-level module serves as the project's root metadata and documentation layer. It contains the Apache 2.0 LICENSE governing distribution terms, a .gitignore defining version control exclusions, and a README.md documenting a quadtree data structure used for geolocation optimization. The module is isolated in the dependency graph, providing no executable code but establishing the legal, tooling, and informational foundation for the repository.

### Context: `geospatial indexing / proximity search`
- **core** — Provides the core QuadTree spatial indexing implementation for geographic neighbor lookup. Defines the `Neighbour` abstraction (id + lat/long), a recursive `QuadTreeNode` that subdivides space into quadrants, and a top-level `QuadTree` facade supporting insertion, removal, and range-based proximity queries. Geographic-distance-to-degree conversions and tuning parameters are centralized in `QuadTreeConstants`. The module is self-contained (isolated in the dependency graph) and intended to be consumed by higher-level visualization or query layers.

### Context: `graphical visualization of spatial quadtree data structures`
- **quadtree** — Provides drawable wrapper classes that adapt the core QuadTree data structures for graphical rendering. `DrawableQuadTree` wraps `QuadTree` and `DrawableQuadTreeNode` wraps `QuadTreeNode`, delegating draw and update operations to render node boundaries, child nodes, and neighbor points with coordinate scaling and translation support.

### Context: `interactive 2d visualization of a quadtree spatial index for geographic nearest-neighbor search`
- **src** — Provides the Swing/AWT-based graphical application shell for visualizing a quadtree-driven geographic point search. It defines the rendering primitives (`BaseObject`, `Drawable`, `Screen`), the animation/input loop in `CanvasPanel` with double buffering and mouse/keyboard pan-and-zoom, the domain-specific `MainScreen` that draws a world map and the quadtree while handling neighbor-search interactions, and the `Main` entry point that wires a `JFrame` to a `CanvasPanel`. This module appears isolated in the supplied graph but at the source level depends on a sibling `src.quadtree` package for the underlying quadtree data structure and neighbour queries.


> _Evidence_: `.gitignore:1`, `LICENSE:1`, `README.md:1` (confidence 0.70)

> _Evidence_: `quadtree-graphic/build.gradle:1`, `quadtree-graphic/gradlew:1`, `quadtree-graphic/gradlew.bat:1` (confidence 0.70)

> _Evidence_: `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties:1` (confidence 0.70)

> _Evidence_: `quadtree-graphic/src/main/java/src/BaseObject.java:1`, `quadtree-graphic/src/main/java/src/CanvasPanel.java:1`, `quadtree-graphic/src/main/java/src/Drawable.java:1` (confidence 0.70)

> _Evidence_: `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java:1`, `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java:1` (confidence 0.70)

> _Evidence_: `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java:1`, `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java:1`, `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java:1` (confidence 0.70)

## Module: `.`
This top-level module serves as the project's root metadata and documentation layer. It contains the Apache 2.0 LICENSE governing distribution terms, a .gitignore defining version control exclusions, and a README.md documenting a quadtree data structure used for geolocation optimization. The module is isolated in the dependency graph, providing no executable code but establishing the legal, tooling, and informational foundation for the repository.

> _Evidence_: `.gitignore:1`, `LICENSE:1`, `README.md:1` (confidence 0.80)

## Module: `quadtree-graphic`
Provides Gradle build infrastructure for the quadtree-graphic Java project, including build configuration (`build.gradle`), project settings (`settings.gradle`), and cross-platform Gradle wrapper scripts (`gradlew`, `gradlew.bat`) for Unix and Windows environments. Targets Java 1.8 with JUnit for testing. This module appears isolated in the dependency graph, suggesting it scaffolds a standalone build environment for a quadtree-based graphical application.

**Public surface:**
- `gradlew`
- `gradlew.bat`
- `build.gradle`
- `settings.gradle`

> _Evidence_: `quadtree-graphic/build.gradle:1`, `quadtree-graphic/gradlew:1`, `quadtree-graphic/gradlew.bat:1` (confidence 0.80)

## Module: `quadtree-graphic/gradle/wrapper`
Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution version (8.5) and defining where the wrapper downloads and stores its distribution files. This ensures reproducible builds across developer machines without requiring a pre-installed Gradle. The module is isolated in the dependency graph, serving purely as build-tooling configuration.

**Public surface:**
- `gradle-wrapper.properties`

> _Evidence_: `quadtree-graphic/gradle/wrapper/gradle-wrapper.properties:1` (confidence 0.80)

## Module: `quadtree-graphic/src/main/java/src`
Provides the Swing/AWT-based graphical application shell for visualizing a quadtree-driven geographic point search. It defines the rendering primitives (`BaseObject`, `Drawable`, `Screen`), the animation/input loop in `CanvasPanel` with double buffering and mouse/keyboard pan-and-zoom, the domain-specific `MainScreen` that draws a world map and the quadtree while handling neighbor-search interactions, and the `Main` entry point that wires a `JFrame` to a `CanvasPanel`. This module appears isolated in the supplied graph but at the source level depends on a sibling `src.quadtree` package for the underlying quadtree data structure and neighbour queries.

**Public surface:**
- `Main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `BaseObject`
- `Drawable`

**Collaborators:**
- `src.quadtree (DrawableQuadTree, QuadTree, Neighbour)`
- `javax.swing/java.awt (JFrame, Canvas, BufferStrategy, Graphics2D)`

> _Evidence_: `quadtree-graphic/src/main/java/src/BaseObject.java:1`, `quadtree-graphic/src/main/java/src/CanvasPanel.java:1`, `quadtree-graphic/src/main/java/src/Drawable.java:1` (confidence 0.80)

## Module: `quadtree-graphic/src/main/java/src/quadtree`
Provides drawable wrapper classes that adapt the core QuadTree data structures for graphical rendering. `DrawableQuadTree` wraps `QuadTree` and `DrawableQuadTreeNode` wraps `QuadTreeNode`, delegating draw and update operations to render node boundaries, child nodes, and neighbor points with coordinate scaling and translation support.

**Public surface:**
- `DrawableQuadTree`
- `DrawableQuadTreeNode`

**Collaborators:**
- `src.Drawable`
- `src.quadtree.core.QuadTree`
- `src.quadtree.core.QuadTreeNode`
- `src.quadtree.core.Neighbour`

> _Evidence_: `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java:1`, `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java:1` (confidence 0.80)

## Module: `quadtree-graphic/src/main/java/src/quadtree/core`
Provides the core QuadTree spatial indexing implementation for geographic neighbor lookup. Defines the `Neighbour` abstraction (id + lat/long), a recursive `QuadTreeNode` that subdivides space into quadrants, and a top-level `QuadTree` facade supporting insertion, removal, and range-based proximity queries. Geographic-distance-to-degree conversions and tuning parameters are centralized in `QuadTreeConstants`. The module is self-contained (isolated in the dependency graph) and intended to be consumed by higher-level visualization or query layers.

**Public surface:**
- `Neighbour`
- `NeighbourImpl`
- `QuadTree`
- `QuadTreeNode`
- `QuadTreeConstants`
- `addNeighbour`
- `removeNeighbour`
- `findNeighbours`
- `findNeighboursIds`
- `findNeighboursWithinRectangle`
- `getRangeAsRectangle`

> _Evidence_: `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java:1`, `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java:1`, `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java:1` (confidence 0.80)
