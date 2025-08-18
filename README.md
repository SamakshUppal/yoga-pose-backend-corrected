# YogaPoseBackend (Corrected)

## Fixes applied
- **Database visibility** → Added `/admin` HTML viewer + paginated API to browse entries.
- **Feedback too fast** → Throttled Socket.IO emits server-side (default 500ms; change via `EMIT_INTERVAL_MS`).
- **Debugged** → Input validation, timestamp ordering, pagination; ready to plug into your frontend.

## Quickstart
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
python app.py
```
- Open http://localhost:5000/health
- Open http://localhost:5000/admin

## REST API
- `POST /api/register` → `{ "username": "alice" }`
- `POST /api/landmarks` → `{ "user_id": 1, "name": "video1", "landmarks": [...] }`
- `GET /api/landmarks/<user_id>?page=1&page_size=25`

## WebSocket (Socket.IO)
- Connect to same origin; listen for `landmark_update`.
- Server throttles emits per user to reduce spam.

## Env
- `DB_URL` for custom database (e.g., Postgres)
- `EMIT_INTERVAL_MS` to adjust live update rate
