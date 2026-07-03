# Module — `quadtree-graphic/src/main/java/src/quadtree/core` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree/core` module supplies a self-contained spatial-indexing engine built around a recursive quadtree decomposition of geographic space. It exposes the `Neighbour` interface and `NeighbourImpl` value type for representing latitude–longitude points with identifiers, the `QuadTreeNode` recursive structure that subdivides regions into quadrants down to a configurable capacity, the `QuadTree` facade offering `addNeighbour` and `findNeighbours` operations for radius queries, and `QuadTreeConstants` for node-sizing parameters and kilometer-to-degree conversions. With eleven public symbols and five files, the module presents a complete API surface for indexing geographic entities and retrieving proximity sets without leaking internals.

The module exhibits zero fan-in and zero fan-out, establishing it as a pure leaf in the dependency graph—isolated both from upstream consumers and downstream dependencies. No other module in the codebase currently imports these types or calls these methods, and `core` itself requires nothing beyond the JDK. This isolation means the spatial-query engine can be tested, versioned, and evolved independently, though it also signals that integration points have yet to materialize in sibling packages. Architects evaluating reuse should note that the lack of observed collaborators leaves composition and lifecycle management entirely to future adopters.

For the complete file inventory and line-level purpose statements within `quadtree-graphic/src/main/java/src/quadtree/core`, see the corresponding entry in the Codebase Guide.

_Domain hint: `Geospatial indexing / proximity search`_

## Responsibility

Provides the core quadtree spatial-indexing data structure for storing and querying geographic neighbours by latitude/longitude. Defines the `Neighbour` contract and its `NeighbourImpl` value type, the recursive `QuadTreeNode` that subdivides space into quadrants, the top-level `QuadTree` facade for adding points and finding neighbours within a radius, and `QuadTreeConstants` for node sizing and km-to-degree conversions. This module is self-contained (isolated in the dependency graph) and serves as a reusable spatial-query engine.

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

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src__quadtree__core.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
