# Module — `quadtree-graphic/src/main/java/src` (LLD)

The `quadtree-graphic/src/main/java/src` module serves as the composition root and presentation layer for the entire quadtree visualization demo, bootstrapping the Swing application in `Main.main` and orchestrating a custom rendering pipeline through `CanvasPanel`. With zero fan-in and zero fan-out at the module level, it sits alone in the dependency graph yet pulls in collaborators `src.quadtree.DrawableQuadTree`, `src.quadtree.core.QuadTree`, and `src.quadtree.core.Neighbour` to assemble the interactive geospatial workload. The seven-symbol public surface—`Drawable`, `BaseObject`, `Screen`, `CanvasPanel`, `MainScreen`, `Main`, and `Main.main`—defines both the application entry point and a small framework for managing drawable entities with dedicated render threads, pan/zoom gestures, and real-time updates.

`MainScreen` exemplifies the module's responsibility: it loads a world map backdrop, populates a `DrawableQuadTree` with ten million random points, and issues radius-based neighbor queries on mouse interaction, bridging domain logic from the `src.quadtree.core` package into the Swing event loop. `CanvasPanel` encapsulates the side-effect surface for rendering, running a separate thread that repaints at a target frame rate and translates `MouseEvent` coordinates into canvas space for panning and zooming. Because no other modules depend on this one, any refactoring of the UI layer remains local, though the lack of fan-in also signals that this is the sole entry point—changes here ripple outward to user-facing behavior immediately.

For the six files constituting this module and their individual purposes, consult the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src`.

_Domain hint: `Interactive geospatial visualization / quadtree demo UI`_

## Responsibility

Provides the Swing-based graphical application shell for the quadtree visualization demo. It defines the rendering framework (`Drawable` interface, `BaseObject` base class, `Screen` collection manager), the interactive `CanvasPanel` with its dedicated render thread handling pan/zoom and mouse/keyboard input, and the `MainScreen` which loads a world map, scatters 10 million random points into a quadtree, and performs radius-based neighbor searches on mouse interaction. `Main` bootstraps the `JFrame` and wires `CanvasPanel` into it.

## At a glance

| Dimension | Value |
|---|---|
| Files | 6 |
| Public surface | 7 symbol(s) |
| Collaborators | 3 |
| Fan-in | 0 module(s) |
| Fan-out | 0 module(s) |

## Public surface

- `Main`
- `Main.main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `BaseObject`
- `Drawable`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/BaseObject.java` | Defines an abstract base class (BaseObject) that represents drawable objects with fundamental spa… | `BaseObject` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java` | This file implements a Canvas panel that manages real-time rendering with a dedicated thread, han… | `CanvasPanel` |
| `quadtree-graphic/src/main/java/src/Drawable.java` | Defines an interface for drawable objects that can be rendered and updated in a graphical applica… | `Drawable` |
| `quadtree-graphic/src/main/java/src/Main.java` | Main entry point and application window setup class that creates a JFrame, initializes a CanvasPa… | `Main`, `main` |
| `quadtree-graphic/src/main/java/src/MainScreen.java` | Implements the main visualization screen for a geographic quadtree demo. It displays a world map… | `MainScreen` |
| `quadtree-graphic/src/main/java/src/Screen.java` | Manages a collection of drawable objects and delegates rendering and update operations to them. P… | `Screen` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
