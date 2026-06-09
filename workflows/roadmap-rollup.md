# Workflow: roadmap rollup

Estimate many projects, then stack them into a single-threaded capacity timeline.

## 0. Two kinds of rollup (they behave differently)
- **Roadmap of distinct projects** (separate one-pagers, unrelated bets) — genuinely
  independent. Stack them; only note shared DS/patterns where they happen to overlap.
- **One project decomposed into slices** (the X-Large → rollup bridge) — the slices ship
  independently but are facets of ONE experience. They ship apart but must be DESIGNED
  together, so they share a foundation. Model it explicitly (step 2.5) or you double-count
  the discovery and the rollup reads far larger than the work actually is.

**The X-Large bridge:** if `estimate-single` reads a project as **X-Large** AND the doc frames
it as independent, shippable slices, proactively OFFER to decompose it into a rollup rather
than just returning "split it with product."

## 1. Gather the project list
Accept one-pagers/PRDs, or existing `*.yaml` data spines. For any without a spine, run
`estimate-single` (SWAG by default) to produce one — a rollup IS the case where the spine is
needed, so generate the `.yaml` here even though single estimates skip it by default.
**Exclude open-ended / unbounded items** ("other quick wins", "continually triage feedback",
etc.) from the totals — flag them as un-sizable scope to fence, do not silently fold them in.

## 2. Stack end-to-end (single-threaded)
Because a designer runs one project at a time, lay the estimates sequentially and compute the
cumulative week range as you go. **Single-threading is a DELIVERY constraint, not a design
one** — one designer can only build one thing at a time, but that does NOT mean each slice is
discovered and framed from scratch. For decomposed projects, see step 2.5 before you sum.

## 2.5 Decomposed projects: extract the shared Foundation (do NOT double-count discovery)
When the slices are facets of one experience, the cross-cutting design thinking happens ONCE,
not once per slice. Pull it into a leading **Foundation** phase and slim the slices:

- **Foundation (runs once, first).** The holistic discovery, the system architecture / IA /
  taxonomy, the shared components & patterns, and the unifying experience vision — the
  "explore them as a unit" work. Typically `Discovery UXR → Explore → Crit → Review`. It is not
  a slice and ships nothing on its own; it's the connective tissue every slice builds on.
- **Slim each slice.** Remove the work the Foundation now covers — above all the per-slice
  **Discovery UXR** (slices inherit it). Keep only what's genuinely slice-specific:
  explore-within-the-system → crit → refine → review, plus a slice's own incremental
  validation/experiment ONLY where its risk is distinct (e.g. an AI slice's accuracy check).
- **Consolidate validation.** Validate the INTEGRATED experience once rather than re-running a
  full Validation UXR inside every slice; keep a slice-local validation only where the risk is
  unique to that slice.
- **Recompute.** Total = Foundation + slimmed slices. This is usually LOWER than the naive
  sum-of-standalone-slices (which double/triple-counts discovery), and it's more honest: it
  surfaces the upfront coherence investment AND removes the duplicated research.

**The tell:** two Large slices each carrying a full Discovery UXR + Validation UXR is the
signature of the double-count — one of those discoveries belongs in the Foundation.

## 3. Sequence by value + dependency
Order by impact / leverage (largest lever first) unless dependencies dictate otherwise. For a
decomposed project the **Foundation is always first**; downstream slices then follow their
dependency order (e.g. "A's taxonomy gates B and C"). State the sequence and why.

## 4. Mark capacity
- Place an H2 / half-boundary marker at the planning horizon (e.g. 13 weeks).
- Flag any project that crosses the boundary as **over-capacity for the half**.
- Total by size (e.g. "Foundation + 1 Large, 2 Medium = ~9-12 wks"). Count the Foundation.

## 4.5 Protect coherence (decomposed projects)
The slices are one experience, so estimate the seams, not just the pieces:
- A **cross-slice coherence review** — once after the Foundation (vision lock) and once near
  the end (does the whole thing still read as one product?).
- A **dependency note** — which slices share surfaces / components, and what unlocks what.
- A **coherence risk** line — design the slices independently, or skip the Foundation, and you
  pay for it in rework and an inconsistent experience.

## 5. Render
Rollup mode of `templates/one-pager.html`: the rollup timeline (a node per slice + cumulative
week markers, lead slice emphasized), the per-slice plans, the half-boundary line, and the
over-capacity flag. Rollup mode OMITS the Design needs section. For a **decomposed project**,
also render the **Foundation** as the leading node on the timeline and as the distinct leading
card in the per-slice plans (the `.foundation` treatment), and add the "designed as one
experience" note so the single-threaded stack doesn't read as three unrelated projects.
Aggregate the spines into a single `roadmap.yaml`.
**Output to the MAIN Rula checkout: `/Users/radwakefield/Rula/H2 Planning/Estimates/roadmap.html`**
(NOT a worktree — the DS `@import` only resolves in the main checkout; see estimate-single.md step 9).
A single X-Large project decomposed into slices renders to `<project-slug>.html` there too.

**After writing the file, auto-open it:** `open "/Users/radwakefield/Rula/H2 Planning/Estimates/roadmap.html"`
(macOS) so the user sees the styled portfolio view immediately.

Commit message: `feat: add roadmap-rollup workflow`
