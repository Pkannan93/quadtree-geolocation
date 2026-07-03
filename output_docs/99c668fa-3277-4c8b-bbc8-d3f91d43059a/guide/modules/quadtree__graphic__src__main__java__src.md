# Module — `quadtree-graphic/src/main/java/src`

_Domain hint: `Interactive 2D graphics / spatial data-structure visualization (quadtree neighbor search over a geographic map)`_

## Responsibility

Provides the top-level Swing/AWT application scaffolding for the quadtree visualization: bootstraps the window (`Main`), hosts a double-buffered rendering canvas with input handling (`CanvasPanel`), defines base abstractions for drawable scene objects (`BaseObject`, `Drawable`, `Screen`), and implements `MainScreen` which renders a world map, overlays an interactive quadtree, and performs radius-based neighbor searches in response to mouse input. This module is the application's entry layer and presentation shell, composing lower-level quadtree data structures into a visual demo.

## Public surface

- `Main`
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
| `quadtree-graphic/src/main/java/src/BaseObject.java` | Defines an abstract base class for drawable objects in a graphics system, providing fundamental p… | `BaseObject`, `mPositionX`, `mPositionY`, … (+2) |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java` | CanvasPanel is a Canvas component that manages a rendering thread to display and interact with a… | `CanvasPanel` |
| `quadtree-graphic/src/main/java/src/Drawable.java` | Defines the Drawable interface, which establishes a contract for graphical objects that can be re… | `Drawable` |
| `quadtree-graphic/src/main/java/src/Main.java` | Entry point and main application frame class that creates and configures the window, initializes… | `Main` |
| `quadtree-graphic/src/main/java/src/MainScreen.java` | MainScreen is the main visualization screen that displays a world map with an interactive quadtre… | `MainScreen` |
| `quadtree-graphic/src/main/java/src/Screen.java` | This file defines a base Screen class that manages a collection of drawable objects (BaseObject i… | `Screen` |

---

See also: [Modules index](index.md) — every module in this run.
