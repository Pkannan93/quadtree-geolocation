# Module — `quadtree-graphic/src/main/java/src` (LLD)

The `quadtree-graphic/src/main/java/src` module serves as the **composition root** for the interactive quadtree visualization application, owning the Swing/AWT shell, the rendering loop, and the drawable abstraction layer. It exports seven public symbols—most critically `Main.main`, the entry point that instantiates a `JFrame`; `CanvasPanel`, which implements double-buffered rendering and input handling; and `MainScreen`, which orchestrates the world-map overlay and neighbor-search visualization by consuming `DrawableQuadTree`, `QuadTree`, and `Neighbour` from the `src.quadtree` collaborator. The module defines the `Drawable` and `BaseObject` contracts that allow arbitrary scene objects to participate in the rendering pipeline, and it aggregates them via the `Screen` container, which dispatches `draw()` and `update()` calls each frame.

With **zero fan-in** and **zero fan-out** at the module level—the sole collaborator being `src.quadtree`—this module sits at the top of the dependency graph, assembling lower-level spatial-index primitives into a runnable GUI. The lack of dependents confirms its role as a leaf composition root: nothing upstream imports from it. The public surface is intentionally wide (seven exports across six files) because this module must expose both the application entry point and the rendering framework for any future screen implementations, though in practice `MainScreen` is the only concrete screen today.

For a complete file-by-file breakdown—including `CanvasPanel.java`, `MainScreen.java`, and the drawable base classes—consult the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src`, which enumerates all six source files and their individual responsibilities.

_Domain hint: `Interactive 2D graphics / spatial-index visualization (quadtree neighbor search on a world map)`_

## Responsibility

Provides the top-level Swing/AWT application shell and rendering loop for the quadtree graphic visualization. It defines the drawable abstractions (`BaseObject`, `Drawable`), a `Screen` container that aggregates and dispatches draw/update calls, a double-buffered `CanvasPanel` that handles the render loop and mouse/keyboard interaction (zoom/pan), the `Main` entry point that boots a `JFrame`, and `MainScreen` which loads a world map image and drives an interactive quadtree neighbor-search visualization.

## At a glance

| Dimension | Value |
|---|---|
| Files | 6 |
| Public surface | 7 symbol(s) |
| Collaborators | 1 |
| Fan-in | 0 module(s) |
| Fan-out | 0 module(s) |

## Public surface

- `Main`
- `main`
- `CanvasPanel`
- `Screen`
- `MainScreen`
- `BaseObject`
- `Drawable`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/BaseObject.java` | Defines an abstract base class for drawable objects in the quadtree graphic system. Provides core… | `BaseObject` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java` | A custom Canvas panel that manages a graphical rendering surface with double-buffering, providing… | `CanvasPanel` |
| `quadtree-graphic/src/main/java/src/Drawable.java` | Defines a generic interface for objects that can participate in a graphics rendering system, requ… | `Drawable` |
| `quadtree-graphic/src/main/java/src/Main.java` | Entry point and main application class that creates and configures a JFrame window to host a Canv… | `Main`, `main` |
| `quadtree-graphic/src/main/java/src/MainScreen.java` | MainScreen is the primary UI component that displays a world map with an interactive quadtree vis… | `MainScreen` |
| `quadtree-graphic/src/main/java/src/Screen.java` | This file defines a Screen class that acts as a container and manager for drawable objects. It ma… | `Screen` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
