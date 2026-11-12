# CI Drill Status

Live-fire drill runbook walkthrough for the on-call rotation.

- Drill CI (push-triggered): intentionally fails with `exit 1` to simulate a broken build on main.
- Drill Soak (manual dispatch only): 20-minute soak test via `sleep 1200`.

This file was added to trigger a fresh Drill CI run for evidence gathering.
