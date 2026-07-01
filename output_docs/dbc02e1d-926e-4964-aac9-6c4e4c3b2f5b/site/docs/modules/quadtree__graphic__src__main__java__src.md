# Module — `quadtree-graphic/src/main/java/src`

_Domain hint: `Interactive 2D spatial-data (quadtree) visualization / geographic point indexing demo`_

## Responsibility

Provides the top-level Swing application shell and rendering framework for a quadtree visualization tool. It defines the application entry point (`Main`), a double-buffered interactive `CanvasPanel` with zoom/pan and input handling, a generic `Screen` container of `Drawable` objects, and the concrete `MainScreen` which renders a quadtree over a world map image, supports mouse-driven nearest-neighbor queries, and runs a background thread that continuously inserts random points. `BaseObject` and the `Drawable` interface provide the abstract primitives that all rendered elements build on. This module is isolated in the dependency graph (no fan-in/fan-out recorded), though at the source level `MainScreen` consumes `src.quadtree.DrawableQuadTree`, `QuadTree`, and `Neighbour` from a sibling quadtree package.

## Public surface

- `Main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `Drawable`
- `BaseObject`

## Collaborators

- `src.quadtree.DrawableQuadTree`
- `src.quadtree.core.QuadTree`
- `src.quadtree.core.Neighbour`

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

See also: [Modules index](index.md) — every module in this run.
