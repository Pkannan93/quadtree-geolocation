# code-analyser-repo-byu4b9o0 — Architecture

This system adopts a **layered architecture** with clean separation between a core domain, a drawable extension layer, and an application shell, all packaged as a single Gradle-built desktop application. The substrate reports zero cycles across six modules and confirms strict acyclicity, indicating disciplined enforcement of dependency direction—no module reaches back toward its dependents. The single-layer count suggests modules are logically flat or that layering is enforced by convention rather than multi-tier partitioning; zero edges in the reported dependency graph imply either module isolation or that inter-module wiring happens at runtime through composition or plugin boundaries rather than compile-time dependencies.

The architecture favors **monolithic deployment with modular boundaries**, trading distribution complexity for simplicity in versioning, transactionality, and local reasoning. The absence of cycles and the low edge count reflect a deliberate pattern: modules likely expose narrow interfaces, with the application shell acting as the composition root that wires the core and drawable layers together at startup. This style supports rapid iteration and a small surface for integration testing, but couples release cycles—changes to the core ripple through to shell redeployment.

Concrete module names, dependency edges, and layer assignments appear in the **Reference › Codebase Guide**, while the Gradle build structure and desktop packaging details are documented under **Operations › Build & Release**.

**Architecture style.** layered (core → drawable extension → application shell), packaged as a single Gradle-built desktop application

## System diagram

_Architecture Mermaid not available — the diagram-generation agent did not run or had no input to emit. See `overview/architecture-diagram.md` for the text breakdown._

## Layers

_Topological layers, leaves first. Modules in layer 0 depend on nothing internal; deeper layers depend on shallower ones. Cyclic SCCs collapse to a single layer._

- **Layer 0** (5 module(s)): `quadtree-graphic`, `quadtree-graphic/gradle/wrapper`, `quadtree-graphic/src/main/java/src`, `quadtree-graphic/src/main/java/src/quadtree`, `quadtree-graphic/src/main/java/src/quadtree/core`


---

**Related surfaces.** [Components](components.md) · [Overview / architecture-diagram](../overview/architecture-diagram.md)
