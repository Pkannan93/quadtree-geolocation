# Geospatial indexing and visualization (quadtree-based proximity search over latitude/longitude points) Documentation — Capability matrix

One row per capability, with its bounded context, the modules that implement it, and the routes it exposes (when an HTTP surface is involved). Routes deep-link into the per-route reference page so readers can pivot from the domain view to the technical contract.

## `build tooling / gradle configuration`

| Capability | Modules | Routes |
|---|---|---|
| **wrapper** | `quadtree-graphic/gradle/wrapper` | — |


## `build tooling / project configuration for a quadtree graphics application`

| Capability | Modules | Routes |
|---|---|---|
| **quadtree-graphic** | `quadtree-graphic` | — |


## `geospatial indexing / spatial data structures`

| Capability | Modules | Routes |
|---|---|---|
| **.** | `.` | — |
| **core** | `quadtree-graphic/src/main/java/src/quadtree/core` | — |


## `interactive 2d graphics / spatial data-structure visualization (quadtree neighbor search over a geographic map)`

| Capability | Modules | Routes |
|---|---|---|
| **src** | `quadtree-graphic/src/main/java/src` | — |


## `spatial data structure visualization / graphical rendering of quadtrees`

| Capability | Modules | Routes |
|---|---|---|
| **quadtree** | `quadtree-graphic/src/main/java/src/quadtree` | — |

