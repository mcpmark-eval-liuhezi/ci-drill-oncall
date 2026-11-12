# ci-drill-oncall

Throwaway public repo hosting the CI incident runbook live-fire drill.

## Workflows

- **Drill CI** (`.github/workflows/drill-ci.yml`) — triggered on `push` and `workflow_dispatch`; contains a job with an intentional `exit 1` failure to simulate a broken build on `main`.
- **Drill Soak** (`.github/workflows/drill-soak.yml`) — manual dispatch only (`workflow_dispatch`); single job that sleeps for ~20 minutes (1200s).

## Tracking issue

Track drill progress in the issue titled `CI drill: broken build on main`.
