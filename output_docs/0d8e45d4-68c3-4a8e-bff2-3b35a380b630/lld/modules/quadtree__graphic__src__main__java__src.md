# Module — `quadtree-graphic/src/main/java/src` (LLD)

The `quadtree-graphic/src/main/java/src` directory serves as the sole composition root for this Java Swing application, binding together the visualization framework, input handling, and rendering loop that demonstrate quadtree spatial queries over a map. With fan-in of zero and fan-out of zero, this module sits at the top of the dependency graph; it pulls in `src.quadtree.DrawableQuadTree` and `src.quadtree.core.QuadTree` from sibling packages but no other module depends on it. `Main.main` bootstraps a `JFrame` around `CanvasPanel`, which implements a continuous render loop using `BufferStrategy` from `java.awt`, while `MainScreen` orchestrates the interactive demo by loading an image via `ImageIO` and wiring mouse events to nearest-neighbor queries.

The public surface—`Main`, `CanvasPanel`, `MainScreen`, `Screen`, `BaseObject`, `Drawable`, and the static entry point `Main.main`—exposes more than a typical application root would. The presence of `Drawable` (an interface), `BaseObject` (an abstract class), and `Screen` (a container) in this top-level package suggests these scene-graph primitives could be factored into a separate reusable layer if the visualization framework ever needs to support additional demos beyond the quadtree use case. As it stands, `MainScreen` directly composes `DrawableQuadTree` from `src.quadtree`, establishing a crisp boundary: core spatial indexing logic remains decoupled from AWT/Swing, and this module owns all side-effect surfaces (window creation, file I/O, render thread).

For the six files that implement this module—including the entry point, the canvas, and the drawable abstractions—consult the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src`, which enumerates each source file and its role in the application lifecycle.

_Domain hint: `Interactive visualization / demo UI for a quadtree spatial-indexing data structure`_

## Responsibility

This module is the top-level application package for a Java Swing/AWT graphical application that visualizes a quadtree spatial data structure over a world map. It bootstraps the JFrame window (`Main`), runs a custom render-loop canvas with zoom/pan and input handling (`CanvasPanel`), and provides the abstract scene-graph primitives (`Drawable` interface, `BaseObject` abstract class, `Screen` container) on top of which `MainScreen` builds an interactive demo that loads a map image, populates a `DrawableQuadTree`, and performs mouse-driven nearest-neighbor queries while reporting performance.

## At a glance

| Dimension | Value |
|---|---|
| Files | 6 |
| Public surface | 7 symbol(s) |
| Collaborators | 5 |
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
| `quadtree-graphic/src/main/java/src/BaseObject.java` | Defines an abstract base class 'BaseObject' for drawable objects that have position (x, y) and di… | `BaseObject` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java` | Provides a custom Canvas-based panel that implements a continuously running render loop with mous… | `CanvasPanel` |
| `quadtree-graphic/src/main/java/src/Drawable.java` | Defines an interface for objects that can be drawn and updated in a graphics context. This interf… | `Drawable` |
| `quadtree-graphic/src/main/java/src/Main.java` | Entry point and main application class that creates and configures a JFrame window, sets up a Can… | `Main`, `main` |
| `quadtree-graphic/src/main/java/src/MainScreen.java` | MainScreen is a GUI screen that visualizes a world map with an interactive quadtree data structur… | `MainScreen` |
| `quadtree-graphic/src/main/java/src/Screen.java` | Manages a collection of drawable objects, providing a base screen class that delegates drawing an… | `Screen` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
