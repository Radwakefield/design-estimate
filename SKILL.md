---
name: design-estimate
description: "Estimates design effort and timeline for a roadmap project using Rula's T-shirt sizing framework and Design Playbooks. Use when sizing a design project, estimating a one-pager or PRD, planning design capacity for a roadmap or half, or producing a design estimate one-pager. Triggers on: estimate this project, how long will this take, size this, t-shirt size, design estimate, design sizing, roadmap planning, capacity planning."
---

# Design estimate

Estimates design effort + timeline from Rula's Design Estimation (T-shirt sizing) framework
and Design Playbooks. Produces a shareable HTML one-pager. A small YAML data spine is OPTIONAL —
emitted only on request or when feeding a roadmap rollup (see `workflows/estimate-single.md` step 9).

## Route by input
- **A one-pager** -> SWAG tier. Read `workflows/estimate-single.md`.
- **A fleshed-out PRD** -> Refined tier (higher confidence). Read `workflows/estimate-single.md`.
- **A list of projects / "roadmap rollup"** -> Read `workflows/roadmap-rollup.md`.
- **"Recalibrate" / reviewing actuals** -> Read `workflows/calibrate.md`.

## Always load
- `references/sizing-matrix.md` - the inputs, outputs, and size-resolution rule.
- `references/block-durations.md` - tunable working-day defaults for the block sum.

## Load as needed
- `references/design-playbooks.md` - building-block + phase definitions.
- `references/quality-bars.md` - one-pager engagement model (SWAG reading lens) + kick-off
  checklist / crit / review (Refined tier).
- `references/calibration-log.md` - past projects (calibrate workflow).

## Core principles
- Two tiers (SWAG one-pager / Refined PRD); same matrix, different confidence.
- Single-threaded: block durations are sequential working days, never concurrent.
- Adaptive interview: ask only where the doc leaves a dimension uncertain.
- Any output is overridable; recompute the block sum when it changes.
- Primary number = matrix week range; block sum is the secondary precision figure.
- The designer is the primary user; the one-pager is for cross-functional + leadership, so
  keep the output plain-language.

## Gotchas
- **A single new component is NOT an automatic Large.** New-component *count* is a modifier —
  one new component on an otherwise-contained project reads Medium (see `sizing-matrix.md`).
- **Never sum block durations concurrently.** Work is single-threaded; durations are
  sequential working days. The rollup stacks projects end-to-end for the same reason.
- **The block sum is advisory, not the headline.** The matrix week range is the primary,
  authoritative number. When an override removes a block, the sum legitimately drops below
  the matrix range — that gap is the expected calibration signal, not an error.
- **Don't fold unbounded items into totals.** "Other quick wins", "continually triage…" can't
  be sized — fence them as explicit out-of-scope, don't silently add them to a rollup.
- **Don't force a size when the three dimensions disagree by >1 size.** That spread is the
  interview trigger — ask, don't guess.
- **Don't trust the author's self-estimate.** Re-derive the size from the dimensions; stated
  "1-2 weeks each" framings are an input to challenge, not accept.
- **X-Large → don't produce a plan.** Recommend splitting with product; if the doc lists
  independent slices, offer the roadmap-rollup decomposition instead.
- **Always write output to the MAIN Rula checkout** (`/Users/radwakefield/Rula/H2 Planning/Estimates/`),
  even when invoked from a git worktree. The one-pager `@import`s the live DS file, which only exists
  in the main checkout — writing to a worktree renders it UNSTYLED. The finalized files there
  (`dbt-improvements.html` rollup, `pick-up-where-you-left-off.html` single) are the styling
  source of truth, NOT a re-inlined/Google-Fonts variant.
