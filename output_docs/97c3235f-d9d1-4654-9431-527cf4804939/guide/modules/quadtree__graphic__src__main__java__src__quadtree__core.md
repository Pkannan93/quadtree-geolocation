# Module — `quadtree-graphic/src/main/java/src/quadtree/core`

_Domain hint: `Geospatial indexing / spatial search (quadtree for geographic neighbour lookup)`_

## Responsibility

Provides the core quadtree spatial indexing engine: defines the `Neighbour` abstraction for geo-located entities (id, latitude, longitude), a concrete `NeighbourImpl` data holder, and the recursive `QuadTreeNode` that partitions latitude/longitude space and stores neighbours at leaves. The top-level `QuadTree` covers the full Earth coordinate range and exposes operations to add neighbours and query them within a kilometre-based range (`addNeighbour`, `findNeighbours`, `findNeighboursIds`, `getRangeAsRectangle`), relying on `QuadTreeConstants` for km-to-degree conversions and coordinate normalization. The module is self-contained (isolated in the dependency graph) and acts as the reusable spatial-search backbone for the quadtree-graphic application.

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

See also: [Modules index](index.md) — every module in this run.
