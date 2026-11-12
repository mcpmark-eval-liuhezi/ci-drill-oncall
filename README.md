# ci-drill-oncall

Throwaway public repo used for a live-fire on-call CI incident runbook drill.

## Workflows

- **Drill CI** (`.github/workflows/drill-ci.yml`) — triggered on `push` and `workflow_dispatch`; job `drill-ci` runs a step that intentionally exits non-zero (`exit 1`) to simulate a broken build on `main`.
- **Drill Soak** (`.github/workflows/drill-soak.yml`) — manual dispatch only (`workflow_dispatch`); single job `drill-soak` sleeps for ~20 minutes (`sleep 1200`) to simulate a long-running soak test.

## Drill sequence

1. Push a change to `main` to start a red Drill CI run.
2. Capture the failed job log as evidence.
3. Open a tracking issue titled `CI drill: broken build on main` with the failed run id.
4. Dispatch the Drill Soak workflow and cancel it while it is in flight.
5. Re-run only the failed jobs of the Drill CI run.
6. Comment `DRILL COMPLETE` on the tracking issue.
