# canvas-repo-whq499lb — Architecture

This system expresses a **layered application** style built around a self-contained spatial-index core library, wrapped by a drawable adapter, and fronted by a presentation shell. The zero-edge, zero-cycle substrate confirms strict acyclic discipline: no module imports another within the reported dependency graph, suggesting either a monolithic single-file deployment or that the six modules represent independent compilation units with integration happening at the runtime composition boundary rather than through compile-time imports. The single-layer classification and absence of top dependency targets reinforce that architectural boundaries are enforced by convention and file organization rather than explicit module-to-module coupling.

This design choice privileges **portability and reuse**—the spatial-index core can be extracted and consumed by other consumers without dragging presentation concerns. The drawable adapter serves as the **abstraction seam** between domain logic and rendering, keeping the core ignorant of visualization. However, the substrate reveals no shared-dependency hot-spots or composition roots, which may indicate either a deliberately minimal API surface or that integration contracts live outside the static module graph (e.g., dependency injection configured in an untracked entry point). The absence of cycles is a strong **layering invariant**, but with zero edges the graph cannot show whether violations are prevented by tooling or simply never attempted.

Concrete module boundaries, import relationships, and entry-point wiring are detailed in the **Codebase Guide**; runtime composition and configuration loading are covered under **Configuration** and **Operations** respectively.

**Architecture style.** layered application with a reusable core library (presentation shell over a drawable adapter over a self-contained spatial-index core)

## System diagram

_Architecture Mermaid not available — the diagram-generation agent did not run or had no input to emit. See `overview/architecture-diagram.md` for the text breakdown._

## Layers

_Topological layers, leaves first. Modules in layer 0 depend on nothing internal; deeper layers depend on shallower ones. Cyclic SCCs collapse to a single layer._

- **Layer 0** (5 module(s)): `quadtree-graphic`, `quadtree-graphic/gradle/wrapper`, `quadtree-graphic/src/main/java/src`, `quadtree-graphic/src/main/java/src/quadtree`, `quadtree-graphic/src/main/java/src/quadtree/core`


---

**Related surfaces.** [Components](components.md) · [Overview / architecture-diagram](../overview/architecture-diagram.md)
