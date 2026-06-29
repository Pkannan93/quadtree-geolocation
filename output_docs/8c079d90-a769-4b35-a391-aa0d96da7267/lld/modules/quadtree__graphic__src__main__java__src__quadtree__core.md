# Module — `quadtree-graphic/src/main/java/src/quadtree/core` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree/core` module implements a recursive spatial indexing engine for efficient neighbour lookups on Earth coordinates. It exposes a public surface of 11 symbols, anchored by the `QuadTree` class that manages the full latitude/longitude grid and operations like `addNeighbour`, `findNeighbours`, and `findNeighboursWithinRectangle`. Beneath `QuadTree`, the `QuadTreeNode` recursively partitions space into quadrants, storing `Neighbour` instances at leaf boundaries, while `QuadTreeConstants` handles kilometre-to-degree conversions and coordinate normalization required by the range queries.

This module exhibits zero fan-in and zero fan-out—it depends on no other application modules and no other modules depend on it. The isolation signals that core is either a leaf module awaiting integration or a standalone library candidate extracted into the quadtree-graphic project but not yet wired to presentation or service layers. The public surface includes both the abstract `Neighbour` interface and the concrete `NeighbourImpl` data holder, indicating that clients may implement custom neighbour types or rely on the provided implementation. The `getRangeAsRectangle` utility suggests that range-based queries return bounding-box metadata alongside neighbour collections, supporting visualisation or further geometric filtering.

For the complete file inventory and per-file responsibilities within this module, consult the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src/quadtree/core`.

_Domain hint: `Geospatial indexing / spatial search (quadtree for geographic neighbour lookup)`_

## Responsibility

Provides the core quadtree spatial indexing engine: defines the `Neighbour` abstraction for geo-located entities (id, latitude, longitude), a concrete `NeighbourImpl` data holder, and the recursive `QuadTreeNode` that partitions latitude/longitude space and stores neighbours at leaves. The top-level `QuadTree` covers the full Earth coordinate range and exposes operations to add neighbours and query them within a kilometre-based range (`addNeighbour`, `findNeighbours`, `findNeighboursIds`, `getRangeAsRectangle`), relying on `QuadTreeConstants` for km-to-degree conversions and coordinate normalization. The module is self-contained (isolated in the dependency graph) and acts as the reusable spatial-search backbone for the quadtree-graphic application.

## At a glance

| Dimension | Value |
|---|---|
| Files | 5 |
| Public surface | 11 symbol(s) |
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
- `getRangeAsRectangle`
- `removeNeighbour`
- `findNeighboursWithinRectangle`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java` | Defines an interface for representing a neighbour entity in a quadtree structure, specifying meth… | `Neighbour` |
| `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java` | This file implements a concrete Neighbour class that stores and provides access to a geographical… | `NeighbourImpl` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java` | This file implements a QuadTree data structure for efficient spatial indexing and searching of ne… | `QuadTree`, `addNeighbour`, `findNeighbours`, … (+2) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java` | This file defines constants and utility methods for the QuadTree implementation, specifically han… | `QuadTreeConstants` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java` | Implements a quadtree spatial data structure node that recursively partitions 2D space using geog… | `QuadTreeNode`, `addNeighbour`, `removeNeighbour`, … (+1) |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src__quadtree__core.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
