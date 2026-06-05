# Block durations (TUNABLE)

Working-day defaults per building block. Work is SINGLE-THREADED: these are sequential
days, never concurrent. Used for the secondary "block sum" precision number. The matrix
week range is the primary, authoritative figure.

| Block | Default (working days) |
|---|---|
| Discovery UXR | 5-10 (1-2 wks) |
| Explore | 2-4 |
| Critique | 0.5 async / 1 live |
| Refine | 1-3 |
| Validation UXR | 5 (~1 wk) |
| Review | 0.5-1 |

## How to compute a block sum
Sum the per-block defaults across the size's project plan (sequentially). Report as a
range (min sum, max sum). The block sum should land INSIDE the matrix week range; if it
doesn't, that is a calibration signal (see calibrate workflow).

## Changelog
- 2026-06-05: Initial defaults. Calibrated so Small ~3-7d, Medium (with validation) ~10-15d,
  Large ~18-25d, matching the matrix ranges. Pending real-world calibration against shipped projects.
- 2026-06-05 (post-validation): block sum is the SECONDARY/advisory figure; the matrix week
  range is primary. When an override removes a block (e.g. Validation UXR ~5d from a Medium),
  the block sum legitimately drops below the matrix range — that gap is the expected
  "calibration signal", not an error. Example: overridden Medium plan [Explore, Critique,
  Refine, Review] sums to ~5-9d (≈1-2 wks), below the 2-3 wk Medium range, flagging a light
  Medium. Fixtures' block_sum_days are derived from this table; recompute them when durations change.
