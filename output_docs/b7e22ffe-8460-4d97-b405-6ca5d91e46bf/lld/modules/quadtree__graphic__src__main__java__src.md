# Module — `quadtree-graphic/src/main/java/src` (LLD)

The `quadtree-graphic/src/main/java/src` module serves as the composition root for a Swing-based geographic quadtree visualizer, housing the application entry point (`Main`) alongside the rendering pipeline (`CanvasPanel`, `Screen`, `MainScreen`) and drawable primitives (`Drawable`, `BaseObject`). It orchestrates the world map display, mouse-driven radius neighbor search, and performance metrics rendering, importing `DrawableQuadTree`, `QuadTree`, and `Neighbour` from the single collaborator `src.quadtree`. With zero fan-in and zero fan-out in the module graph, this is a leaf module in isolation: no other modules depend on its six exported symbols, and it pulls from no sibling modules beyond the internal `src.quadtree` package reference.

The public surface exposes UI framework types (`CanvasPanel`, `MainScreen`) and abstraction contracts (`Drawable`, `Screen`) that together define the visualization domain but see no reuse elsewhere in the codebase. `MainScreen` handles the side-effect surface—loading the world map image, populating a quadtree with geographic coordinates, translating mouse events into search radius queries—while `CanvasPanel` manages the AWT event loop and double-buffered rendering. The absence of dependent modules signals that all Swing integration lives here; any refactoring to extract reusable UI components or decouple rendering logic would need to introduce new module boundaries.

For the file-level breakdown of `Main.java`, `CanvasPanel.java`, and the four other sources inside this directory, see the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src`.

_Domain hint: `Spatial data structure visualization / geographic neighbor search`_

## Responsibility

Provides the top-level Swing/AWT graphical application for visualizing a quadtree of geographic points on a world map. It defines the application entry point (`Main`), the rendering surface and input loop (`CanvasPanel`), a screen abstraction (`Screen`) with a concrete `MainScreen` that loads the world map image, populates a quadtree, and handles mouse-driven radius neighbor searches with performance display. Also defines core drawable abstractions (`Drawable` interface and `BaseObject` base class) used by visual elements. This module is isolated in the dependency graph but internally relies on a `src.quadtree` package for the quadtree data structure and rendering.

## At a glance

| Dimension | Value |
|---|---|
| Files | 6 |
| Public surface | 6 symbol(s) |
| Collaborators | 1 |
| Fan-in | 0 module(s) |
| Fan-out | 0 module(s) |

## Public surface

- `Main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `Drawable`
- `BaseObject`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/BaseObject.java` | Defines an abstract base class for drawable objects in the quadtree graphic system, providing fun… | `BaseObject` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java` | This file provides a custom Canvas component that manages rendering, user input (mouse and keyboa… | `CanvasPanel` |
| `quadtree-graphic/src/main/java/src/Drawable.java` | Defines the Drawable interface, which establishes a contract for objects that can be rendered and… | `Drawable` |
| `quadtree-graphic/src/main/java/src/Main.java` | Main application entry point that creates and configures a JFrame window, initializes a CanvasPan… | `Main`, `main` |
| `quadtree-graphic/src/main/java/src/MainScreen.java` | MainScreen is the primary UI component that displays a world map with a quadtree visualization of… | `MainScreen` |
| `quadtree-graphic/src/main/java/src/Screen.java` | This file defines a base Screen class that manages and coordinates a collection of drawable objec… | `Screen` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
