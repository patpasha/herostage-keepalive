# herostage-keepalive

Small public GitHub Actions workflows for Render-hosted Hero Stage services. The repository is public so scheduled runs do not consume the private app repository's Actions quota.

## Production keepalive

`keep-render-awake.yml` pings the production API every 5 minutes.

Target: `https://heromode-spidey.onrender.com/api/`

## TestFlight Live Activities

`live-activity-tick.yml` wakes the TestFlight backend every 30 minutes and asks it to evaluate due Live Activities. The backend still enforces each user's local checkpoint, fresh-step requirement, opt-out, and once-per-day delivery.

Authentication uses short-lived GitHub OIDC tokens pinned to this repository, workflow, and `main` branch. There is no shared cron secret.

Manual runs: **Actions** → choose a workflow → **Run workflow**.