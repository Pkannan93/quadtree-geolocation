# canvas-repo-g4vao_fy — High-Level Design

This system is a visual demonstration of quadtree spatial indexing for geographic point data. When you need to find all coffee shops within two miles of your current location, or identify the nearest gas station along a highway, a naive scan of every point on a map becomes impractical at scale. A quadtree recursively divides the plane into quadrants, so queries can skip entire regions and return results in logarithmic time instead of checking thousands of irrelevant candidates.

The codebase is organized as a layered stack. At the bottom, the `quadtree/core` package implements the raw spatial index: `QuadTree` and `QuadTreeNode` handle insertion and radius-based proximity search over latitude and longitude pairs, with tuning knobs in `QuadTreeConstants`. One layer up, `DrawableQuadTree` and `DrawableQuadTreeNode` wrap those core types so they can paint themselves on a canvas. At the top, the Swing application in the `src` package (`Main`, `CanvasPanel`, `MainScreen`) ties everything together—loading a world map image, populating the tree with sample points, and letting you click to trigger nearest-neighbor queries while reporting performance metrics.

The Gradle wrapper scripts ensure anyone can build and run the demo without wrestling with toolchain versions. The interactive UI shows the quadtree's recursive subdivisions overlaid on the map, so you can see which branches the algorithm prunes during each query.

The sub-pages below unpack the module structure, walk through the query flow in detail, and document the constants that govern tree depth and bucket size.

## System at a glance

| Dimension | Value |
|---|---|
| Architecture style | layered modular monolith (core spatial library + visualization adapter + Swing UI shell, with separate build scaffolding) |
| Primary domain | Geospatial indexing and visualization (quadtree-based location services) |
| Modules | 6 |
| Parsed files | 21 |
| HTTP routes | 0 |
| Domain entities | 0 |
| Background jobs | 0 |
| Deployment manifests | 0 |
| Bounded contexts | 6 |
| Business capabilities | 6 |

## Dive deeper

- [System context](system-context.md) — what's inside the boundary, what's outside, who talks to it.
- [Components](components.md) — major components, their responsibilities, and the fan-in / fan-out leaders.
- [Architecture](architecture.md) — architectural style, key patterns, layering, and the system diagram.
- [Data flows](data-flows.md) — how requests flow through the system end-to-end for the busiest routes.
- [Integration](integration.md) — external systems this service talks to (DBs, caches, queues, third-party APIs).
- [Deployment](deployment.md) — services, container images, background workers, scaling notes.


---

**Related surfaces.** [Overview](../index.md) · [Codebase Guide](../modules/index.md) · [API Reference](../api/index.md) · [Operations](../operations/index.md)
