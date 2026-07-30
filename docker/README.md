# Docker

Docker configuration files for local development and production.

## Services (docker-compose.yml)

- **postgres** — primary database. Data persisted in the `postgres-data` volume.
- **redis** — cache / queue backend. Data persisted in the `redis-data` volume.
- **pgadmin** — web UI for inspecting the postgres database, waits for postgres to be healthy before starting.

`backend` and `frontend` services are intentionally not defined yet — they will be added once the NestJS and Next.js apps exist (v0.3 / v0.4), each with its own Dockerfile.

All services share the `genesis-network` bridge network and read their configuration from the root `.env` file (see `.env.example`).
