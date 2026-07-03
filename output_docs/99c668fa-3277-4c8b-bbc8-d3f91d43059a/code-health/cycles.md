# Geospatial indexing and visualization (quadtree-based proximity search over latitude/longitude points) Documentation — Cyclic subsystems

Strongly-connected components in the module-dependency graph — modules that import from each other in a closed loop. Each cycle is a real refactor target: in a layered architecture, layer N must not depend on layer N+k.

_No cycles detected — the import graph is a DAG. The fan-in / fan-out leaders on [hotspots.md](hotspots.md) carry the architectural-stress story for this run._