# Workflow: estimate a single project

## 1. Detect tier
- One-pager (short, "under review", thin evidence) -> **SWAG**.
- Fleshed-out PRD -> **Refined**.
- A list of projects -> stop; use `roadmap-rollup.md` instead.
Ask only if genuinely ambiguous.

## 2. Infer the three dimensions
Read the doc. For each of Impact / Scope / Discovery, match against the descriptors in
`references/sizing-matrix.md` and pick a size, quoting the supporting evidence.
**For a one-pager (SWAG), read it through the one-pager engagement model in
`references/quality-bars.md`** — its section→dimension map tells you where each dimension's
evidence lives: Problem statement → Discovery, Solution → Scope, Success criteria → Impact,
Confidence level → Discovery/risk.

## 3. Adaptive, confidence-gated interview
Per dimension:
- **Confident** -> state the read + quoted evidence; move on.
- **Uncertain / evidence missing** -> ask ONE targeted question so the user can supply
  context the doc lacks. Record what you had to ask (it lowers confidence and is auditable).
**SWAG calibration:** run the one-pager readiness checklist (`references/quality-bars.md`) —
problem grounded in evidence? success criteria linked to OKRs (not placeholder `+x%`)? confidence
section names risks/gaps? Each miss lowers confidence, becomes one of your targeted questions, and
lands as a flagged risk in step 10. It does NOT change the size.

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
Render `templates/one-pager.html` (timeline pills + crit/review markers) — the HTML one-pager is the
single default deliverable.

**Write the summary in a human voice.** The lede should read like a thoughtful colleague briefing a
teammate — open with the human problem/intent in plain sentences, THEN land the verdict (size + why it
leans where it does). Do NOT open with "Source one-pager by X" or lead with author/date/status; those
go in the de-emphasized `.byline` line under the lede. See the LEDE/BYLINE notes in the template.
**Output = the MAIN Rula checkout: `/Users/radwakefield/Rula/H2 Planning/Estimates/<project-slug>.html`.**
Write there even when invoked from a git worktree — the one-pager styles itself via
`@import "../../App/Rula Design System/colors_and_type.css"`, and that DS file only exists in the
main checkout. Writing to a worktree renders the page UNSTYLED. Match the finalized estimates already
there (`pick-up-where-you-left-off.html` = single mode, `dbt-improvements.html` = rollup mode).

**After writing the file, auto-open it** so the user can see the styled result immediately:
`open "/Users/radwakefield/Rula/H2 Planning/Estimates/<project-slug>.html"` (macOS). Open the
final rendered HTML only — not the YAML.

**The YAML data spine is OPTIONAL — skip it by default.** Only also write `<project-slug>.yaml`
(from `templates/data-spine.yaml`) when EITHER the user explicitly asks for it, OR this estimate
feeds a roadmap rollup (the rollup stacks projects from their spines — see `roadmap-rollup.md`).
A standalone single estimate does not need one.

## 10. Close
State confidence and "what would tighten this" (the SWAG->PRD upgrade path).
