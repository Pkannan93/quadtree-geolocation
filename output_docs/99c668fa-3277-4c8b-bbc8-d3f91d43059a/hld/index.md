# canvas-repo-whq499lb — High-Level Design

QuadTreeGraphic is a demonstration system that stores geographic points—latitude and longitude pairs—in a quadtree and lets users find all points within a given radius of a clicked location. Quadtrees are tree-shaped data structures that recursively divide two-dimensional space into quarters, making it fast to discard entire regions when answering "which points are near this spot?" The system converts kilometer distances into degrees at query time and visualizes both the tree's internal boundaries and the search results on top of a world map.

The code is organized in three layers. At the bottom, the `quadtree/core` package implements the pure spatial-index logic: inserting points, traversing nodes, and collecting neighbors that fall inside a search circle. One level up, the `quadtree` adapter package wraps those core classes with rendering methods so each tree node knows how to draw itself and its children. At the top, a small Swing application in the `src` package wires together a canvas panel, a background map image, and mouse-event handlers that translate clicks into proximity queries and paint the results interactively.

The repository ships with Gradle build scripts that bundle everything into a runnable application. The wrapper directory ensures a consistent Gradle version across developer machines and continuous-integration environments, while the top-level configuration declares dependencies and output artifacts.

The pages that follow break down the architecture into subsystems, trace the data flow from mouse event to rendered overlay, and document each module's responsibilities. Start with the **System Context** page to see how the pieces connect, then explore **Core Modules** for the quadtree implementation and **Presentation Layer** for the graphical shell.

## System at a glance

| Dimension | Value |
|---|---|
| Architecture style | layered application with a reusable core library (presentation shell over a drawable adapter over a self-contained spatial-index core) |
| Primary domain | Geospatial indexing and visualization (quadtree-based proximity search over latitude/longitude points) |
| Modules | 6 |
| Parsed files | 21 |
| HTTP routes | 0 |
| Domain entities | 0 |
| Background jobs | 0 |
| Deployment manifests | 0 |
| Bounded contexts | 5 |
| Business capabilities | 6 |

## Dive deeper

- [System context](system-context.md) — what's inside the boundary, what's outside, who talks to it.
- [Components](components.md) — major components, their responsibilities, and the fan-in / fan-out leaders.
- [Architecture](architecture.md) — architectural style, key patterns, layering, and the system diagram.
- [Data flows](data-flows.md) — how requests flow through the system end-to-end for the busiest routes.
- [Integration](integration.md) — external systems this service talks to (DBs, caches, queues, third-party APIs).
- [Deployment](deployment.md) — services, container images, background workers, scaling notes.


---

**Related surfaces.** [Overview](../overview/index.md) · [Codebase Guide](../guide/index.md) · [API Reference](../reference/index.md) · [Operations](../operations/index.md)
