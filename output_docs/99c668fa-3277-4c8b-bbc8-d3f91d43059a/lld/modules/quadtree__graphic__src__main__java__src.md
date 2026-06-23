# Module — `quadtree-graphic/src/main/java/src` (LLD)

The `quadtree-graphic/src/main/java/src` module serves as the application's composition root and presentation layer, bootstrapping the Swing/AWT window via `Main` and orchestrating the interactive visualization of quadtree spatial queries over a geographic canvas. Its public surface exports six symbols—`Main`, `CanvasPanel`, `MainScreen`, `Screen`, `BaseObject`, and `Drawable`—that together define the graphics scaffolding and entry point, though zero fan-in indicates no other module depends on these types, confirming this is strictly a top-level shell. The module composes three collaborators from the `src.quadtree` namespace (`DrawableQuadTree`, `QuadTree`, `Neighbour`) to wire domain logic into the rendering loop, with `MainScreen` performing radius-based neighbor searches in response to mouse events and `CanvasPanel` managing double-buffered paint cycles.

With zero fan-out and zero dependency modules, this layer sits at the edge of the dependency graph, consuming spatial-query abstractions but exporting no reusable library surface—a hallmark of an application entry module. The six files inside cleanly separate concerns: `Main.java` launches the frame, `CanvasPanel.java` handles thread-driven rendering, `Screen.java` and `BaseObject.java` provide abstract drawable infrastructure, and `MainScreen.java` implements the concrete map-and-quadtree visualization that exercises the underlying data structure. For a file-by-file breakdown of these responsibilities, consult the Codebase Guide entry for this module.

_Domain hint: `Interactive 2D graphics / spatial data-structure visualization (quadtree neighbor search over a geographic map)`_

## Responsibility

Provides the top-level Swing/AWT application scaffolding for the quadtree visualization: bootstraps the window (`Main`), hosts a double-buffered rendering canvas with input handling (`CanvasPanel`), defines base abstractions for drawable scene objects (`BaseObject`, `Drawable`, `Screen`), and implements `MainScreen` which renders a world map, overlays an interactive quadtree, and performs radius-based neighbor searches in response to mouse input. This module is the application's entry layer and presentation shell, composing lower-level quadtree data structures into a visual demo.

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
- `BaseObject`
- `Drawable`

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

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
