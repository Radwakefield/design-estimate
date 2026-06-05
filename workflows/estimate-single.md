# Workflow: estimate a single project

## 1. Detect tier
- One-pager (short, "under review", thin evidence) -> **SWAG**.
- Fleshed-out PRD -> **Refined**.
- A list of projects -> stop; use `roadmap-rollup.md` instead.
Ask only if genuinely ambiguous.

## 2. Infer the three dimensions
Read the doc. For each of Impact / Scope / Discovery, match against the descriptors in
`references/sizing-matrix.md` and pick a size, quoting the supporting evidence.

## 3. Adaptive, confidence-gated interview
Per dimension:
- **Confident** -> state the read + quoted evidence; move on.
- **Uncertain / evidence missing** -> ask ONE targeted question so the user can supply
  context the doc lacks. Record what you had to ask (it lowers confidence and is auditable).

## 4. Resolve the size
Apply `references/sizing-matrix.md` size-resolution rule: highest-of-three; disagreement
(>1 size spread) -> lower confidence + interview the straddle; new-component count is a
modifier, not an auto-Large.
- X-Large -> recommend splitting with product; do NOT produce a plan.
- Custom -> flag for custom sizing.

## 5. Pull outputs for the size
From the matrix: research, exploration/refinement, feedback cycles, project-plan blocks.

## 6. Offer override + recompute
Let the user override any output (e.g. "no validation UXR"). Record it in `overrides`,
remove/adjust the affected blocks, and RECOMPUTE the block sum. State how the override
shifted the estimate (e.g. "-5 days, now low-end Medium").

## 7. Timeline
- Primary = matrix week range.
- Secondary = block sum from `references/block-durations.md` (sequential, single-threaded),
  reported as a min-max day range. Note if it lands outside the matrix range (calibration signal).

## 8. (Refined tier only) Run the kick-off checklist
Score the PRD against `references/quality-bars.md`. Passed -> can narrow the range + raise
confidence + name exact crit/review steps. Failed items -> flagged risks.

## 9. Emit + render
Fill `templates/data-spine.yaml` and write it next to the one-pager. Render
`templates/one-pager.html` (timeline pills + crit/review markers). Default output dir:
`H2 Planning/Estimates/<project-slug>.html` (+ `.yaml`) in the CALLING repo.

## 10. Close
State confidence and "what would tighten this" (the SWAG->PRD upgrade path).
