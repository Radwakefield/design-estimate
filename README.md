# design-estimate

A Claude Code skill that turns a design one-pager, PRD, or roadmap list into a
defensible **effort + timeline estimate** — using Rula's Design Estimation (T-shirt
sizing) framework and Project Runbook. It produces a shareable, design-system-styled
HTML one-pager you can drop in front of cross-functional partners and leadership.

## Installing & updating

No coding required — these are copy-paste commands you run once in the **Terminal** app
(on a Mac, find it via Spotlight: `⌘ Space`, type "Terminal", hit Enter). Paste a line,
press Enter, and follow any prompts.

> **First time only:** these commands use a tool called `npx` that ships with Node.js.
> If you paste a command and see `command not found: npx`, install Node from
> [nodejs.org](https://nodejs.org) (the "LTS" button), then try again.

**Install it** — copy this line and run it:
```
npx skills add Radwakefield/design-estimate -a claude-code
```
That's it. Open Claude Code and the skill is ready — just paste a one-pager and ask it
to estimate (see "What to say to trigger it" below).

**Update it** — when the skill gets improvements, grab the latest version by running:
```
npx skills update design-estimate
```
(Or `npx skills update` on its own to update every skill you've installed.)

**Check what you have / remove it:**
```
npx skills list                      # see which skills are installed
npx skills remove design-estimate    # uninstall it
```

Updating never touches your past estimates — those are saved files and stay put.

## How it works

The skill doesn't just guess a number — it walks the same path a staff designer would:

1. **Picks a confidence tier.** A short one-pager → a **SWAG** (rough, early-signal)
   estimate. A fleshed-out PRD → a **Refined**, higher-confidence estimate that also
   runs a kick-off quality checklist.
2. **Sizes on three dimensions.** It reads the doc and independently sizes **Impact**
   (how big a bet), **Scope** (surfaces, audiences, components, teams), and **Discovery**
   (how much ambiguity / new research). The size is the *highest* of the three —
   ambiguity and scope rarely shrink.
3. **Interviews you only where the doc is thin.** If a dimension is clear from the doc,
   it states its read and the evidence and moves on. Where the doc leaves it genuinely
   uncertain — or the three reads disagree by more than one size — it asks **one
   targeted question** instead of guessing, and records what it had to ask (that's
   auditable, and it lowers confidence honestly).
4. **Builds a project plan.** It maps the resolved size to a sequence of building blocks
   (Explore → Critique → Validation UXR → Refine → Review, etc.) and a working-day
   **block sum** as a secondary precision figure. The T-shirt **week range** stays the
   headline number.
5. **Lets you override anything.** "No validation research," "this reuses existing
   components," "drop discovery" — it removes the affected blocks and **recomputes** the
   estimate, telling you how the override shifted things.
6. **Renders + auto-opens** a styled HTML one-pager (and, on request, a machine-readable
   YAML data spine).

It's also honest about the edges: a single new component is **not** an automatic Large;
an X-Large gets a "split this with product" recommendation rather than a plan; and an
A/B test being present doesn't by itself make something high-impact.

## What to say to trigger it

Point it at a doc (paste the one-pager, link it, or name it) and ask in plain language.
Any of these work:

**Sizing a single project**
- "Estimate this one-pager."
- "How long will this take to design?"
- "Can you size this project for me?"
- "T-shirt size this feature."
- "What's the design effort here — S/M/L?"
- "Give me a SWAG on this."
- "Estimate this PRD" *(triggers the higher-confidence Refined tier)*

**Planning across multiple projects**
- "Roadmap rollup for these five projects."
- "How much design capacity does H2 need?"
- "Lay these out end-to-end for one designer."
- "Can we fit all of this in the half?"

**Reviewing / recalibrating**
- "This one shipped — recalibrate the model against actuals."
- "Were our estimates off? Let's tune the durations."

**Mid-estimate adjustments** (just say it in conversation)
- "Actually, no validation UXR on this one."
- "Assume it reuses existing components."
- "Bump the confidence — the metrics are now filled in."

## What you get

An HTML one-pager written to `H2 Planning/Estimates/<project-slug>.html` in the calling
repo, styled with the live Rula Design System and **opened automatically** so you can
read it right away. It includes a plain-language summary, the building-block project
plan, the rationale for each dimension, design needs, and the risks / what-would-tighten-this.
A YAML data spine (`<project-slug>.yaml`) is written too when you ask for one or when the
estimate feeds a roadmap rollup.
