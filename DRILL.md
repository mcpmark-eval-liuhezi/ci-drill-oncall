# CI Drill

This repository is a throwaway public repo used to run a live-fire drill against the on-call CI incident runbook.

## Drills performed

- [x] Push-triggered "Drill CI" workflow run (expected to fail intentionally)
- [x] soak workflow dispatched and cancelled while in flight
- [x] re-run of failed jobs on the Drill CI run

## Runbook summary (what to do when a build goes red on main)

1. Find the failed run: https://github.com/mcpmark-eval-liuhezi/ci-drill-oncall/actions
2. Pull the failed job logs to confirm the failure reason.
3. Open a tracking issue with the run id.
4. If a long-running soak job needs to be cut short, cancel the workflow run.
5. Re-run only the failed jobs to verify the fix.
6. Comment on the tracking issue with the outcome and mark the drill complete.
