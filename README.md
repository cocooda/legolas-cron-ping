# Legolas Cron Ping

This repository only keeps the Legolas AI staging backend warm during demo hours.

It does not redeploy Render, call Render deploy hooks, or ping the Retrieval Service directly. The GitHub Actions workflow only sends an HTTP request to the staging backend `/warmup` endpoint.

The schedule is shifted away from exact 10-minute boundaries to reduce GitHub Actions scheduling delays or drops during common high-load cron minutes. GitHub Actions scheduled workflows can still be delayed under high load.

## Schedule

- 08:53, 13:53, 18:53 VN prewarm
- 09:03-12:53 VN every 10 minutes
- 14:03-17:53 VN every 10 minutes
- 19:03-20:53 VN every 10 minutes

## Required Secret

Configure this repository secret without a trailing slash and without `/warmup`:

```text
STAGING_BACKEND_URL=https://legolas-backend-staging.onrender.com
```
