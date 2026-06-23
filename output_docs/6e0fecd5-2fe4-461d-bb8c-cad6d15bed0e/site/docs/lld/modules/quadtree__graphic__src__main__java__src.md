# Module — `quadtree-graphic/src/main/java/src` (LLD)

The `quadtree-graphic/src/main/java/src` module serves as the composition root and sole UI layer for the interactive quadtree visualization, exposing six public symbols: `Main`, `CanvasPanel`, `MainScreen`, `Screen`, `BaseObject`, and `Drawable`. `Main` instantiates a `JFrame` and wires it to `CanvasPanel`, which implements a double-buffered rendering loop with pan-and-zoom controls; `MainScreen` extends `Screen` to paint a world map backdrop and overlay the live quadtree structure retrieved from `src.quadtree.DrawableQuadTree`, while handling mouse clicks to trigger nearest-neighbor queries via `src.quadtree.Neighbour`. The module couples tightly to both the Java Swing/AWT graphics stack and to the sibling `src.quadtree` package, yet the substrate reports zero fan-in and zero fan-out neighbours, indicating this module sits at the boundary of the analyzed dependency graph—likely because `src.quadtree` resides in a parallel source tree not captured in the module list.

This isolation means the reader will not see cyclic edges or layering violations involving `src`, but it also obscures the true coupling: every class in `MainScreen.java` and the rendering chain depends on `QuadTree`, `DrawableQuadTree`, and `Neighbour` from the adjacent package. The public surface is fully exposed with no encapsulation—six top-level types are visible to any caller—though in practice only `Main` is invoked externally. For a complete file inventory and per-file purposes, consult the Codebase Guide entry for `quadtree-graphic/src/main/java/src`.

_Domain hint: `Interactive 2D visualization of a quadtree spatial index for geographic nearest-neighbor search`_

## Responsibility

Provides the Swing/AWT-based graphical application shell for visualizing a quadtree-driven geographic point search. It defines the rendering primitives (`BaseObject`, `Drawable`, `Screen`), the animation/input loop in `CanvasPanel` with double buffering and mouse/keyboard pan-and-zoom, the domain-specific `MainScreen` that draws a world map and the quadtree while handling neighbor-search interactions, and the `Main` entry point that wires a `JFrame` to a `CanvasPanel`. This module appears isolated in the supplied graph but at the source level depends on a sibling `src.quadtree` package for the underlying quadtree data structure and neighbour queries.

## At a glance

| Dimension | Value |
|---|---|
| Files | 6 |
| Public surface | 6 symbol(s) |
| Collaborators | 2 |
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
| `quadtree-graphic/src/main/java/src/BaseObject.java` | Defines an abstract base class for drawable objects in the quadtree graphic system, providing fun… | `BaseObject` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java` | A Canvas panel component that manages a game-like rendering loop with double buffering, handles u… | `CanvasPanel` |
| `quadtree-graphic/src/main/java/src/Drawable.java` | Defines an interface for graphical objects that can be rendered and updated in a graphics context… | `Drawable` |
| `quadtree-graphic/src/main/java/src/Main.java` | Main entry point class that creates and configures the application window (JFrame), sets up a can… | `Main`, `start`, `main` |
| `quadtree-graphic/src/main/java/src/MainScreen.java` | MainScreen serves as the primary visualization and interaction UI for a quadtree-based geographic… | `MainScreen` |
| `quadtree-graphic/src/main/java/src/Screen.java` | This file defines a base Screen class that manages a collection of drawable objects (BaseObject i… | `Screen` |


---

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__src__main__java__src.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
