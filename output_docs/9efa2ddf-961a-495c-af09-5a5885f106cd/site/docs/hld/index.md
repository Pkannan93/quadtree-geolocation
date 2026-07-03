# canvas-repo-s6t9k3sx — High-Level Design

QuadTreeNeighbourSearch is a geospatial toolkit that finds nearby points on Earth quickly. When you have tens of thousands of latitude-longitude coordinates—cities, sensors, delivery stops—and need to answer "which five are closest to me right now?" in milliseconds, a flat list becomes too slow. This system uses a quadtree, a data structure that recursively divides the map into smaller tiles so searches examine only the relevant neighborhood instead of scanning everything.

The engine lives in a core Java package called `quadtree.core`, where classes like `QuadTree` and `QuadTreeNode` build the tree and perform radius searches. A separate drawable layer wraps each node so it can paint itself on screen, and a Swing application shell ties it all together with mouse and keyboard controls. You can zoom, pan, and click anywhere on a world map to see which points fall inside a search radius; the tree's internal tile boundaries appear as nested rectangles so you can watch the spatial partitioning at work. The latitude-longitude math—converting kilometers to degrees, handling the equator versus the poles—happens inside helper methods that the search logic calls automatically.

The repository is structured as a single Gradle project with a handful of directories: the main source tree under `quadtree-graphic/src/main/java`, the Gradle wrapper scripts for reproducible builds, and top-level configuration files. Everything compiles into one runnable JAR. Below you will find detailed breakdowns of the module layout, the core algorithms, and the UI architecture, along with a clickable map of how the pieces connect. If you want to understand the quadtree math, start with the Data Structures page; if you care about the visualization, jump to the UI Components section.

## System at a glance

| Dimension | Value |
|---|---|
| Architecture style | layered (Java application: core data structure → drawable adapter → Swing UI shell), packaged as a single Gradle-built modular monolith |
| Primary domain | Geospatial indexing and visualization — quadtree-based proximity search over latitude/longitude points |
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
