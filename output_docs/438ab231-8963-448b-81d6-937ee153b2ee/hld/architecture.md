# canvas-repo-nkwtyu9g — Architecture

This system adopts a **layered modular monolith** architecture, packaged as a single Gradle-built artifact. The layering flows from core data structures through drawable adapters into a Swing UI shell, a classic separation of domain logic, presentation abstraction, and view concerns. The codebase contains six modules with zero dependency edges recorded, indicating either strong encapsulation via internal coupling or incomplete dependency extraction—the former would be ideal given the layered intent, the latter a gap in static analysis coverage. The architecture is strictly acyclic; no circular dependencies exist to compromise build order or limit incremental compilation.

The single-layer designation reflects a runtime monolith where all modules deploy together, not a violation of logical layering. The zero-edge graph suggests modules either communicate through stable interfaces with minimal cross-references, or internal package-private coupling dominates. The absence of recorded top dependency targets reinforces this: no composition root or central orchestrator surfaces in the static view, which may indicate deferred wiring (runtime classpath assembly) or a flat peer structure where Swing components wire themselves. The drawable adapter layer likely implements the **Adapter pattern** to translate domain entities into Swing-renderable forms, preserving the boundary between business logic and UI framework coupling.

Concrete module names, dependency flows, and layering violations—if any—are detailed in the **Reference > Codebase Guide** and **hld/modules** pages, where per-module fan-out and adapter compositions will clarify the architectural intent.

**Architecture style.** layered (Java application: core data structure → drawable adapter → Swing UI shell), packaged as a single Gradle-built modular monolith

## System diagram

_Architecture Mermaid not available — the diagram-generation agent did not run or had no input to emit. See `overview/architecture-diagram.md` for the text breakdown._

## Layers

_Topological layers, leaves first. Modules in layer 0 depend on nothing internal; deeper layers depend on shallower ones. Cyclic SCCs collapse to a single layer._

- **Layer 0** (5 module(s)): `quadtree-graphic`, `quadtree-graphic/gradle/wrapper`, `quadtree-graphic/src/main/java/src`, `quadtree-graphic/src/main/java/src/quadtree`, `quadtree-graphic/src/main/java/src/quadtree/core`


---

**Related surfaces.** [Components](components.md) · [Overview / architecture-diagram](../overview/architecture-diagram.md)
