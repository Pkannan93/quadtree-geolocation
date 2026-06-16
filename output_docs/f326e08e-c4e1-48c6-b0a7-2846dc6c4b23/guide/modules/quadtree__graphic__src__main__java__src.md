# Module — `quadtree-graphic/src/main/java/src`

_Domain hint: `Spatial data structure visualization / geographic neighbor search`_

## Responsibility

Provides the top-level Swing/AWT graphical application for visualizing a quadtree of geographic points on a world map. It defines the application entry point (`Main`), the rendering surface and input loop (`CanvasPanel`), a screen abstraction (`Screen`) with a concrete `MainScreen` that loads the world map image, populates a quadtree, and handles mouse-driven radius neighbor searches with performance display. Also defines core drawable abstractions (`Drawable` interface and `BaseObject` base class) used by visual elements. This module is isolated in the dependency graph but internally relies on a `src.quadtree` package for the quadtree data structure and rendering.

## Public surface

- `Main`
- `CanvasPanel`
- `MainScreen`
- `Screen`
- `Drawable`
- `BaseObject`

## Collaborators

- `src.quadtree (DrawableQuadTree, QuadTree, Neighbour)`

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

See also: [Modules index](index.md) — every module in this run.
