# Module — `quadtree-graphic/src/main/java/src/quadtree/core` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree/core` module implements a self-contained spatial indexing library with zero fan-in and zero fan-out, positioning it as a pure leaf module that neither depends on nor is consumed by other modules in this codebase. Its responsibility centers on recursive subdivision of geographic space: the `QuadTree` facade accepts `Neighbour` points (via `NeighbourImpl` carrying id, latitude, longitude) and delegates insertion and radius-based search to `QuadTreeNode`, which recursively partitions according to `QuadTreeConstants` thresholds. The public surface exports `addNeighbour`, `findNeighbours`, and `findNeighboursIds` alongside the core types, offering a complete API for kilometer-radius proximity queries without external coupling.

The absence of collaborators signals that this module was designed for embedding—other modules should depend *on* it, yet the substrate shows no inbound edges. This isolation simplifies unit testing and reuse but also suggests the module may be orphaned or that consuming code resides outside the analyzed tree. The `QuadTreeConstants` file centralizes km-to-degree conversion and minimum node size, ensuring that tuning spatial resolution requires touching only one artifact. Because `QuadTreeNode` handles recursive split logic internally, the module encapsulates both the data structure and the geometric reasoning, reducing the surface area clients must understand.

For file-level details—including the `Neighbour` interface contract, `NeighbourImpl` field layout, and `QuadTreeNode` subdivision heuristics—consult the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src/quadtree/core`, which enumerates all five source files and their individual purposes.

_Domain hint: `Geospatial indexing / proximity search`_

## Responsibility

Provides a self-contained quadtree spatial indexing core for geographic data. Defines the `Neighbour` abstraction for points with id and lat/lon coordinates (`NeighbourImpl`), recursive node subdivision and search via `QuadTreeNode`, and the public `QuadTree` facade for inserting points and querying neighbors within a kilometer-based radius. `QuadTreeConstants` centralizes minimum node size configuration and km-to-degree conversion. The module is isolated (no internal fan-in/fan-out), making it a standalone library suitable for embedding in spatial-search applications.

## At a glance

| Dimension | Value |
|---|---|
| Files | 5 |
| Public surface | 8 symbol(s) |
| Collaborators | 0 |
| Fan-in | 0 module(s) |
| Fan-out | 0 module(s) |

## Public surface

- `Neighbour`
- `NeighbourImpl`
- `QuadTree`
- `QuadTreeNode`
- `QuadTreeConstants`
- `addNeighbour`
- `findNeighbours`
- `findNeighboursIds`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java` | Defines the Neighbour interface for objects that represent spatial neighbors in a quadtree struct… | `Neighbour` |
| `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java` | This file provides a concrete implementation of the Neighbour interface, representing a geographi… | `NeighbourImpl` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java` | Implements a QuadTree data structure for efficient spatial indexing and querying of geographic ne… | `QuadTree`, `addNeighbour`, `findNeighbours`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java` | Defines configuration constants for quadtree data structures, including minimum node sizes in bot… | `QuadTreeConstants` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java` | Implements a QuadTreeNode class for spatial indexing, managing geographic bounds divided into fou… | `QuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__src__main__java__src__quadtree__core.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
