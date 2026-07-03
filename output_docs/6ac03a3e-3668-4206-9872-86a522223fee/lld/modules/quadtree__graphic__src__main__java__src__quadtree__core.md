# Module — `quadtree-graphic/src/main/java/src/quadtree/core` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree/core` module delivers the spatial indexing engine at the heart of the application, encapsulating the recursive subdivision logic for geographic coordinate lookups. It exports a public surface of eleven symbols including the `Neighbour` interface, its concrete `NeighbourImpl`, the top-level `QuadTree` orchestrator, the recursive `QuadTreeNode` subdivision structure, and `QuadTreeConstants` which codifies threshold parameters such as `QUADTREE_LAST_NODE_SIZE_IN_KM` and the degree-to-kilometer conversion factor `ONE_DEGREE_IN_KM`. This set of primitives supports insertion via `addNeighbour` and radius-bounded proximity queries through `findNeighbours` and `findNeighboursIds`.

Architecturally this module is a leaf with zero fan-in and zero fan-out, operating in complete isolation from the rest of the codebase. No collaborator modules import from it, no upstream dependencies constrain its implementation, and its self-contained design makes it a candidate for extraction into a separate library. The absence of cyclic dependencies and side-effect surface reflects a purely functional spatial indexing contract, though the lack of downstream consumers suggests either the module is not yet integrated or the application wires these types through reflection or a separate composition root elsewhere in the tree.

For the five files that implement these responsibilities—ranging from the `Neighbour` interface definition to the recursive node logic in `QuadTreeNode.java`—consult the Codebase Guide entry for `quadtree-graphic/src/main/java/src/quadtree/core`, which enumerates each artifact and its internal purpose.

_Domain hint: `Geospatial indexing / spatial data structures`_

## Responsibility

Provides the core quadtree spatial indexing implementation for geographic data. Defines the `Neighbour` abstraction (with a concrete `NeighbourImpl`) representing identifiable points by latitude/longitude, and exposes a `QuadTree` that recursively subdivides space via `QuadTreeNode` to support insertion (`addNeighbour`) and radius-based proximity queries (`findNeighbours`, `findNeighboursIds`). `QuadTreeConstants` centralizes configuration such as the minimum node size and degree-to-kilometer conversion. This module is self-contained (isolated in the dependency graph) and serves as the reusable spatial indexing engine for the broader quadtree-graphic application.

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
- `QUADTREE_LAST_NODE_SIZE_IN_KM`
- `QUADTREE_LAST_NODE_SIZE_IN_DEGREE`
- `ONE_DEGREE_IN_KM`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java` | Defines the Neighbour interface, which represents a spatial object with an identifier and geograp… | `Neighbour` |
| `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java` | Implements the Neighbour interface to provide a concrete representation of a geographical neighbo… | `NeighbourImpl`, `getId`, `getLatitude`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java` | Implements a quadtree data structure for efficient spatial indexing and querying of neighbors bas… | `QuadTree`, `addNeighbour`, `findNeighbours`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java` | Defines global constants for quadtree configuration, including the minimum node size in both kilo… | `QuadTreeConstants`, `QUADTREE_LAST_NODE_SIZE_IN_KM`, `QUADTREE_LAST_NODE_SIZE_IN_DEGREE`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java` | Implements a QuadTreeNode that represents a node in a quadtree spatial data structure for efficie… | `QuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src__quadtree__core.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
