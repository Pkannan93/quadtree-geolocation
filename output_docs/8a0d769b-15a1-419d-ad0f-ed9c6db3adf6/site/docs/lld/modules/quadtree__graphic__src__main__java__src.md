# Module — `quadtree-graphic/src/main/java/src` (LLD)

The `quadtree-graphic/src/main/java/src` module owns the standalone Swing GUI driver for the quadtree visualizer, exposing six public symbols that form a layered rendering stack: `Main` bootstraps the JFrame, `CanvasPanel` runs the double-buffered game loop with pan/zoom input, `Screen` and `BaseObject` provide the drawable object lifecycle, and `MainScreen` orchestrates the concrete world-map quadtree visualization with neighbor search. This module has zero fan-in and zero fan-out at the module level, making it a composition root isolated from the rest of the dependency graph; it directly imports `src.quadtree.DrawableQuadTree`, `src.quadtree.core.QuadTree`, and `src.quadtree.core.Neighbour` as collaborators, consuming the quadtree library but not being consumed by anything else.

Because the module sits at the top of the call chain with no dependents, changes here cannot ripple to other modules, but its role as the sole entry point means it couples tightly to the domain logic it imports—`MainScreen.java` embeds the coordinate system, random point generation, and search UI. The six-file structure keeps the rendering abstractions (`Drawable`, `Screen`) separate from the application shell (`Main`, `CanvasPanel`), though all reside in the same package and share the public surface.

For the full file listing and per-file purpose summaries within this module, see the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src`.

_Domain hint: `Interactive geospatial quadtree visualization (Swing GUI)`_

## Responsibility

Provides the top-level Swing application shell and rendering framework for the quadtree graphic visualizer. It bootstraps the JFrame (`Main`), runs a double-buffered game loop with pan/zoom input handling (`CanvasPanel`), defines the rendering abstractions (`Screen`, `Drawable`, `BaseObject`), and implements the concrete world-map quadtree visualization with random neighbor point generation and interactive search (`MainScreen`). This module is isolated in the dependency graph and serves as the standalone GUI driver layer that consumes the quadtree library internally.

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
| `quadtree-graphic/src/main/java/src/BaseObject.java` | Defines an abstract base class for drawable objects in a graphical system. Provides position (x,… | `BaseObject` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java` | CanvasPanel is a JPanel subclass that provides a game loop with double buffering, handling mouse/… | `CanvasPanel` |
| `quadtree-graphic/src/main/java/src/Drawable.java` | Defines an interface for objects that can be drawn and updated in the animation loop. This serves… | `Drawable` |
| `quadtree-graphic/src/main/java/src/Main.java` | Main entry point and application frame for a quadtree graphics application. Sets up the JFrame wi… | `Main` |
| `quadtree-graphic/src/main/java/src/MainScreen.java` | Serves as the main screen/application entry point that visualizes a geographic quadtree on a worl… | `MainScreen` |
| `quadtree-graphic/src/main/java/src/Screen.java` | This file defines a base Screen class that manages a collection of drawable objects and provides… | `Screen` |


---

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__src__main__java__src.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
