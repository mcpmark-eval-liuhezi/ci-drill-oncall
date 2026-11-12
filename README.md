# CI Drill oncall

Throwaway public repo used to walk the CI incident runbook end-to-end.

 workflows:
 - Drill CI (`.github/workflows/drill-ci.yml`): runs on push and manual dispatch; the `drill-ci` job intentionally fails (`exit 1`) to simulate a broken build on main.
 - Drill Soak (`.github/workflows/drill-soak.yml`): manual dispatch only; the `drill-soak` job sleeps for ~20 minutes.

This commit exists purely to trigger a fresh Drill CI run against main.
