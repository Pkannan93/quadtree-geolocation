# Module — `quadtree-graphic/src/main/java/src` (LLD)

The `quadtree-graphic/src/main/java/src` module serves as the composition root and presentation layer for an interactive quadtree visualization tool. It exposes six public symbols—`Main`, `CanvasPanel`, `MainScreen`, `Screen`, `Drawable`, and `BaseObject`—that together implement the Swing application shell, double-buffered rendering loop, zoom/pan input handling, and the abstract contracts (`Drawable`, `BaseObject`) that define how spatial elements draw themselves. `Main` bootstraps the UI and instantiates `MainScreen`, which coordinates the continuous insertion of random points, mouse-driven nearest-neighbor queries, and the rendering of `DrawableQuadTree` overlaid on a world map image.

Despite being the top-level orchestrator, this module reports zero fan-in and zero fan-out in the dependency graph, a layering anomaly that suggests the build metadata may not capture source-level coupling. In practice `MainScreen` consumes `src.quadtree.DrawableQuadTree`, `src.quadtree.core.QuadTree`, and `src.quadtree.core.Neighbour` from a sibling package, making it a direct client of the spatial-indexing logic rather than an isolated UI shell. This tight binding means changes to the quadtree core surface—particularly the neighbour-query contract—will ripple directly into the rendering thread and input handlers.

For the six implementation files that constitute this module's internal structure, including `CanvasPanel.java` (interactive surface) and `Screen.java` (drawable collection manager), consult the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src`, which enumerates each file's purpose and coordinates.

_Domain hint: `Interactive 2D spatial-data (quadtree) visualization / geographic point indexing demo`_

## Responsibility

Provides the top-level Swing application shell and rendering framework for a quadtree visualization tool. It defines the application entry point (`Main`), a double-buffered interactive `CanvasPanel` with zoom/pan and input handling, a generic `Screen` container of `Drawable` objects, and the concrete `MainScreen` which renders a quadtree over a world map image, supports mouse-driven nearest-neighbor queries, and runs a background thread that continuously inserts random points. `BaseObject` and the `Drawable` interface provide the abstract primitives that all rendered elements build on. This module is isolated in the dependency graph (no fan-in/fan-out recorded), though at the source level `MainScreen` consumes `src.quadtree.DrawableQuadTree`, `QuadTree`, and `Neighbour` from a sibling quadtree package.

## At a glance

| Dimension | Value |
|---|---|
| Files | 6 |
| Public surface | 6 symbol(s) |
| Collaborators | 3 |
| Fan-in | 0 module(s) |
| Fan-out | 0 module(s) |

## Public surface

- `Main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `Drawable`
- `BaseObject`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/BaseObject.java` | Defines an abstract base class (BaseObject) that represents drawable objects in a coordinate syst… | `BaseObject` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java` | A custom canvas panel component that provides an interactive rendering surface with zoom, pan, an… | `CanvasPanel` |
| `quadtree-graphic/src/main/java/src/Drawable.java` | Defines the Drawable interface contract for objects that can be rendered and updated in each fram… | `Drawable` |
| `quadtree-graphic/src/main/java/src/Main.java` | Main entry point and application window class for the quadtree graphic application. Creates and c… | `Main`, `start`, `main` |
| `quadtree-graphic/src/main/java/src/MainScreen.java` | This file implements the main screen component that visualizes a quadtree data structure on a wor… | `MainScreen` |
| `quadtree-graphic/src/main/java/src/Screen.java` | This file defines a base Screen class that manages a collection of drawable objects and provides… | `Screen` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
