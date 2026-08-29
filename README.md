### Hexlet tests and linter status:
[![Actions Status](https://github.com/snicksnk/ai-for-developers-project-386/actions/workflows/hexlet-check.yml/badge.svg)](https://github.com/snicksnk/ai-for-developers-project-386/actions)

## Booking Calendar

Live demo: **https://booking-calendar-bk66.onrender.com**

- Guest booking flow: `/`
- Owner dashboard: `/owner`
- API docs (Swagger UI): `/docs`

### Docker

A multi-stage [`Dockerfile`](./Dockerfile) builds the Vite frontend and the
Fastify backend into a single image. One container serves both the SPA and the
API, listening on `$PORT` (default `4010`) on `0.0.0.0`.

```bash
docker build -t booking-calendar .
docker run -e PORT=8080 -p 8080:8080 booking-calendar
# open http://localhost:8080
```

### Deploy

Deployed to [Render](https://render.com) from [`render.yaml`](./render.yaml)
(Docker runtime, autodeploy on push to `main`). Render injects `$PORT` at
runtime. The same image deploys unchanged to Railway or any Docker host.
