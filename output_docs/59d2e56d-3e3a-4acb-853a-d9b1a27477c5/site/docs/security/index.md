# System Documentation — Security

<!-- alpha8-narrative:overview -->
## Overview

This page is generated directly from the repository's substrate. The tables and citations below summarise everything the analysis pipeline detected for the Security surface; refer to the cited file paths and line numbers for the source of truth.

> _Narrative overlay unavailable in this run — LLM adapter returned a placeholder. The data below is unaffected._
<!-- /alpha8-narrative:overview -->
Reviewer-ready snapshot of the system's auth posture, environment configuration touchpoints, and any literal credentials the static scan caught. Every row links to the page that backs it with file:line citations.

| Signal | Count | Status | Page |
|---|---|---|---|
| Routes with auth required | 0 of 0 (—) | _no routes_ | [auth-summary.md](auth-summary.md) |
| Open (unauth) routes | 0 | 🟢 none | [route-auth-matrix.md](route-auth-matrix.md) |
| Environment variables read | 0 | 🟢 minimal | [secrets-config.md](secrets-config.md) |
| Suspected secret literals | 0 | 🟢 none | [secrets-config.md](secrets-config.md) |
| Config-file references | 0 | 🟢 minimal | [secrets-config.md](secrets-config.md) |

Bands are heuristic and intentionally cautious for security signals: **any** suspected secret literal flips the band to 🔴 because each candidate warrants a manual review, even when the match shape is low-confidence.
