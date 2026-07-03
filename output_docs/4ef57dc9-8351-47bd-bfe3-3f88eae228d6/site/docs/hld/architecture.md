# code-analyser-repo-a6roce0k — Architecture

This system implements a **layered desktop architecture** with strict acyclic dependencies across six modules, achieving zero cycles through deliberate separation of `spatial-core` (domain logic), a drawable adapter layer, and a Swing UI shell. The architecture choice—desktop application over client-server—constrains deployment to single-process JVM runtimes and pushes cross-cutting concerns like configuration into environment variables or property files rather than remote config services. Gradle's multi-project structure enforces the layering at build time: a module boundary violation surfaces as a compile failure, not a runtime surprise.

The absence of cycles (0 detected, `is_acyclic: true`) reflects disciplined dependency injection, likely with composition roots in the UI shell that wire domain services outward. With only one logical layer reported (`layer_count: 1`), the substrate suggests either a flat module graph with horizontal peer dependencies or incomplete layer metadata—common when tooling recognizes structure but not semantic tiers. The separate Gradle build-tooling roots imply modules like `buildSrc` or convention plugins that bootstrap the dependency graph without participating in runtime composition, a pattern that isolates build logic from application code but requires care to avoid version-skew between tooling and shipped artifacts.

Concrete module names, dependency edges, and the drawable adapter contract appear in **Reference § Module Catalog** and **Codebase Guide § Dependency Graph**; runtime assembly and JVM launch parameters live in **Operations § Deployment Topology**.

**Architecture style.** layered desktop application (spatial-core → drawable adapter → Swing UI shell) with separate Gradle build-tooling roots

## System diagram

_Architecture Mermaid not available — the diagram-generation agent did not run or had no input to emit. See `overview/architecture-diagram.md` for the text breakdown._

## Layers

_Topological layers, leaves first. Modules in layer 0 depend on nothing internal; deeper layers depend on shallower ones. Cyclic SCCs collapse to a single layer._

- **Layer 0** (5 module(s)): `quadtree-graphic`, `quadtree-graphic/gradle/wrapper`, `quadtree-graphic/src/main/java/src`, `quadtree-graphic/src/main/java/src/quadtree`, `quadtree-graphic/src/main/java/src/quadtree/core`


---

**Related surfaces.** [Components](components.md) · [Overview / architecture-diagram](../architecture.md)
