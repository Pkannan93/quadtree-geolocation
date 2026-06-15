# Module — `quadtree-graphic/src/main/java/src`

_Domain hint: `Interactive geospatial quadtree visualization (Swing GUI)`_

## Responsibility

Provides the top-level Swing application shell and rendering framework for the quadtree graphic visualizer. It bootstraps the JFrame (`Main`), runs a double-buffered game loop with pan/zoom input handling (`CanvasPanel`), defines the rendering abstractions (`Screen`, `Drawable`, `BaseObject`), and implements the concrete world-map quadtree visualization with random neighbor point generation and interactive search (`MainScreen`). This module is isolated in the dependency graph and serves as the standalone GUI driver layer that consumes the quadtree library internally.

## Public surface

- `Main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `Drawable`
- `BaseObject`

## Collaborators

- `src.quadtree.DrawableQuadTree`
- `src.quadtree.core.QuadTree`
- `src.quadtree.core.Neighbour`

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

See also: [Modules index](index.md) — every module in this run.
