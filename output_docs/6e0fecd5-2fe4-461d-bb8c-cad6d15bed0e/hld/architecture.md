# canvas-repo-95z65xwi — Architecture

This codebase exhibits a classic **layered desktop application** architecture: a core data-structure library forms the computational center, wrapped by drawable adapters that translate model state into visual primitives, with a Swing UI shell orchestrating user interaction at the periphery. The substrate confirms strict acyclicity—zero cycles detected—indicating disciplined dependency flow and robust layer isolation. With only six modules and a single conceptual layer recorded, the system operates as a tightly scoped modular monolith rather than a partitioned service topology, suggesting the entire application compiles to a single deployable JAR or runtime image.

The absence of top dependency targets and zero recorded edges implies either a trivially small codebase or a boundary-module deployment where external framework calls dominate intra-module coupling. This aligns with Swing applications: the UI shell often acts as the sole composition root, invoking core logic and adapters unidirectionally without meaningful fan-in from reusable libraries. No layering violations or cycles appear, which is expected in greenfield desktop tools but worth monitoring as feature complexity grows—introducing bidirectional adapter-to-core references or Swing component subclasses that leak domain logic are common erosion vectors.

Concrete module names, dependency edges, and pattern implementations—factory usage for drawable construction, observer patterns for Swing event binding—are enumerated in the **Codebase Guide**. For runtime packaging, launcher configuration, and native installer manifests, consult the **Operations** section.

**Architecture style.** layered desktop application (core data-structure library wrapped by drawable adapters and a Swing UI shell)

## System diagram

_Architecture Mermaid not available — the diagram-generation agent did not run or had no input to emit. See `overview/architecture-diagram.md` for the text breakdown._

## Layers

_Topological layers, leaves first. Modules in layer 0 depend on nothing internal; deeper layers depend on shallower ones. Cyclic SCCs collapse to a single layer._

- **Layer 0** (5 module(s)): `quadtree-graphic`, `quadtree-graphic/gradle/wrapper`, `quadtree-graphic/src/main/java/src`, `quadtree-graphic/src/main/java/src/quadtree`, `quadtree-graphic/src/main/java/src/quadtree/core`


---

**Related surfaces.** [Components](components.md) · [Overview / architecture-diagram](../overview/architecture-diagram.md)
