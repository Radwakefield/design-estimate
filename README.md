# design-estimate

A Claude Code skill that estimates design effort + timeline for a roadmap project,
using Rula's Design Estimation (T-shirt sizing) framework and Project Runbook.

## Install
```
npx skills add Radwakefield/design-estimate -a claude-code
```

## Use
- "Estimate this project" + a one-pager → a SWAG estimate (size, week range, project plan).
- "Estimate this PRD" → a Refined, higher-confidence estimate.
- "Roadmap rollup" + a list of projects → a single-threaded capacity timeline.

Outputs an HTML one-pager (+ a YAML data spine) to `H2 Planning/Estimates/` in the calling repo.
