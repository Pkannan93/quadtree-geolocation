# canvas-repo-95z65xwi — Components

This system decomposes into six modules arranged in a single layer with zero internal dependencies—a fully decoupled architecture where no module imports another within the analyzed codebase boundary. The absence of fan-in and fan-out leaders suggests either that these modules expose top-level entry points consumed externally (CLI commands, HTTP handlers, serverless functions) or that shared abstractions live outside the scanned perimeter, possibly in a separate package or runtime-provided context. Without edges, there is no composition root in the classical sense; each module likely bootstraps its own dependencies or relies on dependency injection configured at the deployment layer rather than in code.

This flat topology eliminates layering violations and import cycles by design, but it also implies trade-offs: shared logic must be factored into external libraries or duplicated, and cross-cutting concerns—logging, configuration, observability—cannot be centralized through compile-time composition. If the modules represent microservices or isolated Lambda functions, this structure is typical; if they're meant to collaborate within a monolith, the zero-edge graph may reflect incomplete static analysis or runtime-only wiring through service locators or message brokers.

Concrete module names, dependency manifests, and bootstrap logic are documented in the **Codebase Guide**. Infrastructure and runtime wiring—environment variable schemas, service discovery, IAM roles—are covered under **Configuration** and **Operations**.

## Most depended-on components

_Module dependency graph not available — falling back to a flat module list under Codebase Guide._


---

**Related surfaces.** [Codebase Guide (per-module pages)](../modules/index.md) · [Architecture](architecture.md)
