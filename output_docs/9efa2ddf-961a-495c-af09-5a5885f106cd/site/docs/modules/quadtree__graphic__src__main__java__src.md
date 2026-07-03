# Module — `quadtree-graphic/src/main/java/src`

_Domain hint: `Interactive 2D graphics / spatial-index visualization (quadtree neighbor search on a world map)`_

## Responsibility

Provides the top-level Swing/AWT application shell and rendering loop for the quadtree graphic visualization. It defines the drawable abstractions (`BaseObject`, `Drawable`), a `Screen` container that aggregates and dispatches draw/update calls, a double-buffered `CanvasPanel` that handles the render loop and mouse/keyboard interaction (zoom/pan), the `Main` entry point that boots a `JFrame`, and `MainScreen` which loads a world map image and drives an interactive quadtree neighbor-search visualization.

## Public surface

- `Main`
- `main`
- `CanvasPanel`
- `Screen`
- `MainScreen`
- `BaseObject`
- `Drawable`

## Collaborators

- `src.quadtree (DrawableQuadTree, QuadTree, Neighbour)`

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

See also: [Modules index](index.md) — every module in this run.
