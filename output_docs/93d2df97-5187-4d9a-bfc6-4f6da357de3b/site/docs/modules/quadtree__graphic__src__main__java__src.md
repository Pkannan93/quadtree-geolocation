# Module — `quadtree-graphic/src/main/java/src`

_Domain hint: `Interactive 2D visualization of a quadtree spatial index for geographic nearest-neighbor search`_

## Responsibility

Provides the Swing/AWT-based graphical application shell for visualizing a quadtree-driven geographic point search. It defines the rendering primitives (`BaseObject`, `Drawable`, `Screen`), the animation/input loop in `CanvasPanel` with double buffering and mouse/keyboard pan-and-zoom, the domain-specific `MainScreen` that draws a world map and the quadtree while handling neighbor-search interactions, and the `Main` entry point that wires a `JFrame` to a `CanvasPanel`. This module appears isolated in the supplied graph but at the source level depends on a sibling `src.quadtree` package for the underlying quadtree data structure and neighbour queries.

## Public surface

- `Main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `BaseObject`
- `Drawable`

## Collaborators

- `src.quadtree (DrawableQuadTree, QuadTree, Neighbour)`
- `javax.swing/java.awt (JFrame, Canvas, BufferStrategy, Graphics2D)`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/BaseObject.java` | Defines an abstract base class for drawable objects in the quadtree graphic system, providing fun… | `BaseObject` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java` | A Canvas panel component that manages a game-like rendering loop with double buffering, handles u… | `CanvasPanel` |
| `quadtree-graphic/src/main/java/src/Drawable.java` | Defines an interface for graphical objects that can be rendered and updated in a graphics context… | `Drawable` |
| `quadtree-graphic/src/main/java/src/Main.java` | Main entry point class that creates and configures the application window (JFrame), sets up a can… | `Main`, `start`, `main` |
| `quadtree-graphic/src/main/java/src/MainScreen.java` | MainScreen serves as the primary visualization and interaction UI for a quadtree-based geographic… | `MainScreen` |
| `quadtree-graphic/src/main/java/src/Screen.java` | This file defines a base Screen class that manages a collection of drawable objects (BaseObject i… | `Screen` |

---

See also: [Modules index](index.md) — every module in this run.
