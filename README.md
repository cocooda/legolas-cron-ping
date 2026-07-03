# Legolas Cron Ping

This repository only keeps the Legolas AI staging backend warm during demo hours.

It does not redeploy Render, call Render deploy hooks, or ping the Retrieval Service directly. The GitHub Actions workflow only sends an HTTP request to the staging backend `/warmup` endpoint.

## Required Secret

Configure this repository secret:

```text
STAGING_BACKEND_URL=https://legolas-backend-staging.onrender.com
```
