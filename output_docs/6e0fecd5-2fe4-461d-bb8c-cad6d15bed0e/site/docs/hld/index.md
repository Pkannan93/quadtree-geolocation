# canvas-repo-95z65xwi — High-Level Design

QuadGeo is an interactive desktop application that helps you visualize how geographic nearest-neighbor search works under the hood. When you have millions of latitude-longitude points scattered across a map—coffee shops, power poles, weather stations—finding the closest few to any given location becomes slow if you check every point one by one. QuadGeo solves this by organizing coordinates into a quadtree, a data structure that recursively divides the plane into quadrants so queries can skip entire regions that lie too far away. The application lets you pan, zoom, and click anywhere on a canvas to watch the search algorithm highlight relevant quadrants and draw lines to nearby neighbors in real time.

The codebase is organized in three layers. At the bottom, `quadtree-graphic/src/main/java/src/quadtree/core` holds the spatial index itself: `QuadTree` and `QuadTreeNode` handle insertion, removal, and proximity queries, while `QuadTreeConstants` converts geographic distances into the degree tolerances that define search radii. The middle layer, living in `quadtree-graphic/src/main/java/src/quadtree`, wraps these core structures with rendering metadata—`DrawableQuadTree` and `DrawableQuadTreeNode` attach colors and bounds so each node can paint itself onto a canvas. At the top sits the Swing user interface in `quadtree-graphic/src/main/java/src`, where `Main` launches the window, `MainScreen` wires up controls, and `CanvasPanel` listens for mouse events and delegates the actual drawing.

Gradle manages the build, targeting Java 1.8 and bundling JUnit for tests. The repository includes wrapper scripts in `quadtree-graphic/gradle/wrapper` so any developer can compile and run the application without installing Gradle separately.

The pages below unpack each layer in more detail: module dependencies, key algorithms, and the lifecycle of a nearest-neighbor query from mouse-click to rendered result.

## System at a glance

| Dimension | Value |
|---|---|
| Architecture style | layered desktop application (core data-structure library wrapped by drawable adapters and a Swing UI shell) |
| Primary domain | Geospatial indexing and visualization (quadtree-based nearest-neighbor search) |
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
