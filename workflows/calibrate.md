# Workflow: calibrate block durations

Keep the duration layer honest as real projects ship.

## 1. Read actuals
Read `references/calibration-log.md`. Use rows where an Actual is recorded.

## 2. Compare
For each calibrated project, recompute its block sum from current
`references/block-durations.md` defaults. Compare block sum vs actual and vs the matrix range.

## 3. Propose tuned durations
Where block sums systematically over/under-shoot actuals, PROPOSE adjusted per-block defaults
(show old -> new + the evidence). Do not change silently.

## 4. Apply + log
On approval, update `references/block-durations.md` and add a dated entry to its Changelog.
Re-run the fixture suite (tests/) to confirm nothing regressed.

Commit message: `feat: add calibrate workflow`
