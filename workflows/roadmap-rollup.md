# Workflow: roadmap rollup

Estimate many projects, then stack them into a single-threaded capacity timeline.

## 0. When to use (incl. the X-Large -> rollup bridge)
Use for a list of projects. ALSO: if `estimate-single` reads a project as **X-Large** AND the
doc frames it as independent, shippable slices, proactively OFFER to decompose it into a
rollup of smaller projects rather than just returning "split it with product."

## 1. Gather the project list
Accept one-pagers/PRDs, or existing `*.yaml` data spines. For any without a spine, run
`estimate-single` (SWAG by default) to produce one — a rollup IS the case where the spine is
needed, so generate the `.yaml` here even though single estimates skip it by default.
**Exclude open-ended / unbounded items**
("other quick wins", "continually triage feedback", etc.) from the totals — flag them as
un-sizable scope to fence, do not silently fold them into the sum.

## 2. Stack end-to-end (single-threaded)
Because a designer runs one project at a time, lay the estimates sequentially. Compute the
cumulative week range as you go (sum of each project's matrix range).

## 3. Sequence by value
Order slices by impact / leverage (largest lever first) unless dependencies dictate
otherwise. State the recommended sequence and why (e.g. "AVOB first — biggest L2P lever").

## 4. Mark capacity
- Place an H2 / half-boundary marker at the planning horizon (e.g. 13 weeks).
- Flag any project that crosses the boundary as **over-capacity for the half**.
- Total by size (e.g. "2 Large, 3 Medium, 1 Small = ~16-22 wks").

## 5. Render
Produce a portfolio HTML view using rollup mode of `templates/one-pager.html`: the rollup
timeline (a node per slice + cumulative week markers, lead slice emphasized) plus the
per-slice plans, the half-boundary line, and the over-capacity flag. Rollup mode OMITS the
Design needs section. Aggregate the spines into a single `roadmap.yaml`.
**Output to the MAIN Rula checkout: `/Users/radwakefield/Rula/H2 Planning/Estimates/roadmap.html`**
(NOT a worktree — the DS `@import` only resolves in the main checkout; see estimate-single.md step 9).
A single X-Large project decomposed into slices renders to `<project-slug>.html` there too.

Commit message: `feat: add roadmap-rollup workflow`
