# Module — `quadtree-graphic/src/main/java/src`

_Domain hint: `Interactive geospatial visualization / quadtree demo UI`_

## Responsibility

Provides the Swing-based graphical application shell for the quadtree visualization demo. It defines the rendering framework (`Drawable` interface, `BaseObject` base class, `Screen` collection manager), the interactive `CanvasPanel` with its dedicated render thread handling pan/zoom and mouse/keyboard input, and the `MainScreen` which loads a world map, scatters 10 million random points into a quadtree, and performs radius-based neighbor searches on mouse interaction. `Main` bootstraps the `JFrame` and wires `CanvasPanel` into it.

## Public surface

- `Main`
- `Main.main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `BaseObject`
- `Drawable`

## Collaborators

- `src.quadtree.DrawableQuadTree`
- `src.quadtree.core.QuadTree`
- `src.quadtree.core.Neighbour`

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

See also: [Modules index](index.md) — every module in this run.
