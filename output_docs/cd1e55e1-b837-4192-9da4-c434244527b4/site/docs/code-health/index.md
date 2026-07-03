# System Documentation — Code Health

<!-- alpha8-narrative:overview -->
## Overview

This page is generated directly from the repository's substrate. The tables and citations below summarise everything the analysis pipeline detected for the Code Health surface; refer to the cited file paths and line numbers for the source of truth.

> _Narrative overlay unavailable in this run — LLM adapter returned a placeholder. The data below is unaffected._
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
