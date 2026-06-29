# Module — `quadtree-graphic/src/main/java/src`

_Domain hint: `Spatial indexing visualization / interactive geographic data rendering`_

## Responsibility

Provides the Swing/AWT-based graphical application shell for visualizing a quadtree spatial index. It defines the window entry point (`Main`), the rendering surface and input handling (`CanvasPanel`), the scene composition and demo logic that populates 10M geographic neighbors and runs interactive radius searches (`MainScreen`), and base abstractions for drawable entities (`Drawable`, `BaseObject`, `Screen`). The module is isolated in the dependency graph but internally depends on a `src.quadtree` package for the underlying quadtree data structure (`QuadTree`, `Neighbour`, `DrawableQuadTree`).

## Public surface

- `Main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `BaseObject`
- `Drawable`

## Collaborators

- `src.quadtree (DrawableQuadTree, QuadTree, Neighbour)`

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

See also: [Modules index](index.md) — every module in this run.
