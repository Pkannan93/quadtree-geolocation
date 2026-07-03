# Geospatial indexing and visualization — quadtree-based proximity search over latitude/longitude points Documentation — Code Health

<!-- alpha8-narrative:overview -->
## Overview

This page aggregates code health signals that typically guide refactoring priorities and technical debt conversations. The analysis scans the repository for complexity hotspots, TODO and FIXME annotations, and other maintainability indicators that engineering teams watch over time.

The current snapshot shows no hotspots detected and zero TODO or FIXME markers logged. This suggests either a very small codebase, a recent cleanup pass, or that the analysis has not yet captured files where these signals typically appear. It may also indicate that developers are tracking technical debt through issue trackers rather than inline comments.

Use the tables below to verify coverage and confirm whether the empty result reflects the actual state of the repository or points to scope that should be expanded in future scans.
<!-- /alpha8-narrative:overview -->
What might be worth cleaning up, grouped by signal. Each row links to a page with file:line citations and grouping by module.

| Signal | Count | Status | Page |
|---|---|---|---|
| Marker comments (TODO / FIXME / HACK / XXX / NOTE / OTHER) | 0 | 🟢 healthy | [markers.md](markers.md) |
| Deprecated APIs | 0 | 🟢 healthy | [deprecated.md](deprecated.md) |
| Dead-code candidates | 3 | 🟡 watch | [dead-code.md](dead-code.md) |
| Coupling hotspots | 0 | 🟢 healthy | [hotspots.md](hotspots.md) |
| Cyclic subsystems | 0 | 🟢 healthy | [cycles.md](cycles.md) |

Bands are heuristic: 🟢 below the lower threshold, 🟡 in the middle, 🔴 above the upper. The thresholds are tuned for typical service codebases — calibrate against your team's own working agreements before treating any band as a hard alert.
