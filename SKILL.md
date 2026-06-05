---
name: design-estimate
description: Estimate design effort and timeline for a roadmap project using Rula's T-shirt sizing framework and project runbook. Use when sizing a design project, estimating a one-pager or PRD, planning design capacity for a roadmap or half, or producing a design estimate one-pager. Triggers on: estimate this project, how long will this take, size this, t-shirt size, design estimate, design sizing, roadmap planning, capacity planning.
---

# Design estimate

Estimates design effort + timeline from Rula's Design Estimation (T-shirt sizing) framework
and Project Runbook. Produces a shareable HTML one-pager + a YAML data spine.

## Route by input
- **A one-pager** -> SWAG tier. Read `workflows/estimate-single.md`.
- **A fleshed-out PRD** -> Refined tier (higher confidence). Read `workflows/estimate-single.md`.
- **A list of projects / "roadmap rollup"** -> Read `workflows/roadmap-rollup.md`.
- **"Recalibrate" / reviewing actuals** -> Read `workflows/calibrate.md`.

## Always load
- `references/sizing-matrix.md` - the inputs, outputs, and size-resolution rule.
- `references/block-durations.md` - tunable working-day defaults for the block sum.

## Load as needed
- `references/runbook-phases.md` - building-block + phase definitions.
- `references/quality-bars.md` - kick-off checklist / crit / review (Refined tier).
- `references/calibration-log.md` - past projects (calibrate workflow).

## Core principles
- Two tiers (SWAG one-pager / Refined PRD); same matrix, different confidence.
- Single-threaded: block durations are sequential working days, never concurrent.
- Adaptive interview: ask only where the doc leaves a dimension uncertain.
- Any output is overridable; recompute the block sum when it changes.
- Primary number = matrix week range; block sum is the secondary precision figure.
- The designer is the primary user; the one-pager is for cross-functional + leadership, so
  keep the output plain-language.
