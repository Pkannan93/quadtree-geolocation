# Module — `quadtree-graphic/src/main/java/src/quadtree/core`

_Domain hint: `Geospatial indexing / proximity search`_

## Responsibility

Provides the core quadtree spatial-indexing data structure for storing and querying geographic neighbours by latitude/longitude. Defines the `Neighbour` contract and its `NeighbourImpl` value type, the recursive `QuadTreeNode` that subdivides space into quadrants, the top-level `QuadTree` facade for adding points and finding neighbours within a radius, and `QuadTreeConstants` for node sizing and km-to-degree conversions. This module is self-contained (isolated in the dependency graph) and serves as a reusable spatial-query engine.

## Public surface

- `Neighbour`
- `NeighbourImpl`
- `QuadTree`
- `QuadTreeNode`
- `QuadTreeConstants`
- `addNeighbour`
- `findNeighbours`
- `findNeighboursIds`
- `getId`
- `getLatitude`
- `getLongitude`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java` | Defines an interface for representing a neighbour entity with an identifier and geographic locati… | `Neighbour` |
| `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java` | Implements the Neighbour interface to represent a geographical neighbour with an identifier and c… | `NeighbourImpl`, `getId`, `getLatitude`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java` | Implements a quadtree data structure for spatial indexing and efficient querying of neighbors bas… | `QuadTree`, `addNeighbour`, `findNeighbours`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java` | Defines constants for quadtree node sizing and provides conversion utilities between kilometers a… | `QuadTreeConstants` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java` | Implements a quadtree spatial data structure node that recursively subdivides geographic space in… | `QuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
