# Nexus SMS Bridge Server

A lightweight `aiohttp` service that bridges Android SMS app events to web clients over WebSockets.

## Deploy

This repository is deployment-ready:

- Start command is defined in [Procfile](Procfile)
- Railway deployment config is defined in [railway.json](railway.json)
- Health check endpoint: `/health`
- Dynamic port support via `PORT` environment variable

### Steps

1. Click a deploy button above.
2. Set environment variables from [.env.example](.env.example).
3. Deploy.

## Environment Variables

- `PORT`: set by Railway automatically.
- `PUBLIC_BASE_URL`: recommended production URL for QR payload generation.
- `CORS_ORIGINS`: optional comma-separated browser origins.

## Local Run

```bash
pip install -r requirements.txt
python server.py
```

Server endpoints:

- `/` web page
- `/new-session` create a bridge session
- `/session-status/{token}` session status
- `/ws/{token}?role=phone|client` websocket endpoint
- `/health` health check
