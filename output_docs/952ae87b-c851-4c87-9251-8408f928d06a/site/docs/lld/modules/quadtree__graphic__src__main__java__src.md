# Module — `quadtree-graphic/src/main/java/src` (LLD)

The `quadtree-graphic/src/main/java/src` module serves as the composition root and application shell for a Swing/AWT-based geographic visualization system that stress-tests a quadtree spatial index with 10 million neighbors and interactive radius queries. Its public surface (`Main`, `CanvasPanel`, `MainScreen`, `Screen`, `BaseObject`, `Drawable`) exports both the entry point and the full rendering pipeline, making this a top-level orchestrator rather than a reusable library. With zero fan-in and zero fan-out at the module level, it sits isolated in the dependency graph, though it internally consumes `src.quadtree` (specifically `QuadTree`, `Neighbour`, `DrawableQuadTree`) for the underlying spatial indexing logic.

The six-file module combines window lifecycle (`Main.java` creates the JFrame), input/rendering surface (`CanvasPanel.java` handles mouse events and paint cycles), demo scene orchestration (`MainScreen.java` populates the quadtree and executes search queries), and drawable entity abstractions (`Drawable`, `BaseObject`, `Screen`). Because all these concerns live in a single module with no dependents, the side-effect surface is unbounded—`MainScreen` directly couples UI event handling, bulk data generation, and algorithmic search visualization. The lack of fan-in signals that no other module reuses this rendering infrastructure, reinforcing its role as a demo harness rather than a layered graphics subsystem.

For file-level details—including the canvas double-buffering strategy, the 10M-neighbor initialization sequence, and the `Screen` lifecycle contract—consult the Codebase Guide entry for `quadtree-graphic/src/main/java/src`, which enumerates all six source files and their individual responsibilities.

_Domain hint: `Spatial indexing visualization / interactive geographic data rendering`_

## Responsibility

Provides the Swing/AWT-based graphical application shell for visualizing a quadtree spatial index. It defines the window entry point (`Main`), the rendering surface and input handling (`CanvasPanel`), the scene composition and demo logic that populates 10M geographic neighbors and runs interactive radius searches (`MainScreen`), and base abstractions for drawable entities (`Drawable`, `BaseObject`, `Screen`). The module is isolated in the dependency graph but internally depends on a `src.quadtree` package for the underlying quadtree data structure (`QuadTree`, `Neighbour`, `DrawableQuadTree`).

## At a glance

| Dimension | Value |
|---|---|
| Files | 6 |
| Public surface | 6 symbol(s) |
| Collaborators | 1 |
| Fan-in | 0 module(s) |
| Fan-out | 0 module(s) |

## Public surface

- `Main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `BaseObject`
- `Drawable`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/BaseObject.java` | Defines an abstract base class for drawable objects in the quadtree graphic system, encapsulating… | `BaseObject` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java` | A Canvas-based panel component that provides the main rendering surface and input handling for a… | `CanvasPanel` |
| `quadtree-graphic/src/main/java/src/Drawable.java` | Defines an interface for objects that can be drawn and updated in the graphics system. Provides a… | `Drawable` |
| `quadtree-graphic/src/main/java/src/Main.java` | Main entry point for the quadtree graphic application. Creates and configures a JFrame window wit… | `Main` |
| `quadtree-graphic/src/main/java/src/MainScreen.java` | MainScreen is a visual application that demonstrates quadtree spatial indexing by rendering a wor… | `MainScreen` |
| `quadtree-graphic/src/main/java/src/Screen.java` | Manages a collection of drawable objects (BaseObject instances) and provides lifecycle methods to… | `Screen` |


---

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__src__main__java__src.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
