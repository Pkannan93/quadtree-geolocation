# Module — `quadtree-graphic/src/main/java/src`

_Domain hint: `Interactive graphical visualization of a quadtree spatial index over geographic points`_

## Responsibility

Provides the top-level Swing/AWT application shell for the quadtree visualization: bootstraps the JFrame (`Main`), hosts a game-loop rendering canvas with zoom/pan and input handling (`CanvasPanel`), and defines the `Screen`/`Drawable`/`BaseObject` abstractions that structure renderable entities. Its concrete `MainScreen` composes a `DrawableQuadTree` over a world-map background, generates random points, and dispatches mouse-driven neighbour queries against the underlying `QuadTree`.

## Public surface

- `Main`
- `Main.start`
- `Main.main`
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
| `quadtree-graphic/src/main/java/src/BaseObject.java` | Defines an abstract base class for drawable objects in a graphical system, providing core propert… | `BaseObject` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java` | CanvasPanel provides a Canvas-based UI component that manages interactive graphical rendering wit… | `CanvasPanel` |
| `quadtree-graphic/src/main/java/src/Drawable.java` | Defines an interface for drawable objects that can be rendered and updated each frame in the quad… | `Drawable` |
| `quadtree-graphic/src/main/java/src/Main.java` | Main entry point class for the quadtree-graphic application. Creates and configures the JFrame wi… | `Main`, `Main.start`, `Main.main` |
| `quadtree-graphic/src/main/java/src/MainScreen.java` | MainScreen is the primary visualization screen that displays a quadtree structure overlaid on a w… | `MainScreen` |
| `quadtree-graphic/src/main/java/src/Screen.java` | This file defines a base Screen class that manages a collection of drawable objects, coordinates… | `Screen` |

---

See also: [Modules index](index.md) — every module in this run.
