# Module — `quadtree-graphic/src/main/java/src`

_Domain hint: `Interactive visualization / demo UI for a quadtree spatial-indexing data structure`_

## Responsibility

This module is the top-level application package for a Java Swing/AWT graphical application that visualizes a quadtree spatial data structure over a world map. It bootstraps the JFrame window (`Main`), runs a custom render-loop canvas with zoom/pan and input handling (`CanvasPanel`), and provides the abstract scene-graph primitives (`Drawable` interface, `BaseObject` abstract class, `Screen` container) on top of which `MainScreen` builds an interactive demo that loads a map image, populates a `DrawableQuadTree`, and performs mouse-driven nearest-neighbor queries while reporting performance.

## Public surface

- `Main`
- `Main.main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `BaseObject`
- `Drawable`

## Collaborators

- `src.quadtree (DrawableQuadTree)`
- `src.quadtree.core (QuadTree, Neighbour)`
- `javax.swing (JFrame)`
- `java.awt (Canvas, BufferStrategy)`
- `javax.imageio.ImageIO`

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

See also: [Modules index](index.md) — every module in this run.
