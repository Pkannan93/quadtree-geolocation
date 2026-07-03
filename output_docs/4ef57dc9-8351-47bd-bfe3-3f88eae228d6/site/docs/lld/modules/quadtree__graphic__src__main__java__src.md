# Module — `quadtree-graphic/src/main/java/src` (LLD)

The `quadtree-graphic/src/main/java/src` module serves as the composition root for the entire interactive visualization, bridging Swing/AWT infrastructure to the spatial index domain. It exposes `Main` and `Main.start` as the application entry points, alongside `CanvasPanel` for game-loop rendering with zoom, pan, and input dispatch. The public surface also includes `Screen`, `Drawable`, and `BaseObject`—the abstraction triad that structures the rendering pipeline—and `MainScreen`, which wires a `DrawableQuadTree` over a world-map background and routes mouse events to the underlying `src.quadtree.core.QuadTree` and `src.quadtree.core.Neighbour` queries.

With zero fan-in and zero fan-out at the module level, this unit sits at the top of the dependency graph, consuming domain collaborators (`src.quadtree.DrawableQuadTree`, `src.quadtree.core.QuadTree`, `src.quadtree.core.Neighbour`) but exporting none of its own symbols to peer modules. Its public surface of eight names is broad for a leaf module, reflecting its dual role: bootstrapping the JFrame and defining the foundational graphics abstractions that `MainScreen` and future screens would inherit. The module contains no degraded files and cleanly separates application lifecycle (`Main.java`), canvas mechanics (`CanvasPanel.java`), and scene orchestration (`MainScreen.java`, `Screen.java`).

For a file-by-file breakdown—including `BaseObject.java`, `Drawable.java`, and the remaining concrete implementations—consult the Codebase Guide entry for `quadtree-graphic/src/main/java/src`.

_Domain hint: `Interactive graphical visualization of a quadtree spatial index over geographic points`_

## Responsibility

Provides the top-level Swing/AWT application shell for the quadtree visualization: bootstraps the JFrame (`Main`), hosts a game-loop rendering canvas with zoom/pan and input handling (`CanvasPanel`), and defines the `Screen`/`Drawable`/`BaseObject` abstractions that structure renderable entities. Its concrete `MainScreen` composes a `DrawableQuadTree` over a world-map background, generates random points, and dispatches mouse-driven neighbour queries against the underlying `QuadTree`.

## At a glance

| Dimension | Value |
|---|---|
| Files | 6 |
| Public surface | 8 symbol(s) |
| Collaborators | 3 |
| Fan-in | 0 module(s) |
| Fan-out | 0 module(s) |

## Public surface

- `Main`
- `Main.start`
- `Main.main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `Drawable`
- `BaseObject`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/BaseObject.java` | Defines an abstract base class for drawable objects in a graphical system, providing core propert… | `BaseObject` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java` | CanvasPanel provides a Canvas-based UI component that manages interactive graphical rendering wit… | `CanvasPanel` |
| `quadtree-graphic/src/main/java/src/Drawable.java` | Defines an interface for drawable objects that can be rendered and updated each frame in the quad… | `Drawable` |
| `quadtree-graphic/src/main/java/src/Main.java` | Main entry point class for the quadtree-graphic application. Creates and configures the JFrame wi… | `Main`, `Main.start`, `Main.main` |
| `quadtree-graphic/src/main/java/src/MainScreen.java` | MainScreen is the primary visualization screen that displays a quadtree structure overlaid on a w… | `MainScreen` |
| `quadtree-graphic/src/main/java/src/Screen.java` | This file defines a base Screen class that manages a collection of drawable objects, coordinates… | `Screen` |


---

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__src__main__java__src.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
