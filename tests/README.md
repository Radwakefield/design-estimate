# Validation fixtures

These are the regression suite for the estimate logic. There is no automated runner —
LLM-skill output is validated by running the flow and comparing to the expected YAML.

## How to validate
For each `*.expected.yaml` that has a matching input (or a known project name):
1. Run `workflows/estimate-single.md` on the input (use recorded interview answers where present).
2. Compare the produced data spine to the `*.expected.yaml`.
3. PASS = size, week_range, dimensions, project_plan, and any overrides match.
   block_sum_days may vary within +/- 1 day as durations are tuned.

## Calibration
When a fixture's real-world actual is known, add it to `references/calibration-log.md`
and re-check that the block-sum still lands in range.
