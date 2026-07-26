# ADR-008

## Title

Use Pino as the structured logging library for the backend.

---

## Status

Accepted

---

## Context

The backend has no defined logging strategy. Without structured logs, debugging issues in Docker or production environments relies on ad-hoc `console.log` statements that are hard to search, filter or ship to a log aggregator.

---

## Decision

The NestJS backend will use Pino (via `nestjs-pino`) for structured, JSON-based logging. Log level is configurable through an environment variable, defaulting to `info` in production and `debug` in development.

---

## Consequences

### Positive

- Structured JSON logs, easy to parse and ship to external tools.
- Low performance overhead compared to alternatives.
- Request-scoped logging with correlation data via NestJS interceptors.

### Negative

- Logs are less human-readable in raw form during local development (mitigated with `pino-pretty` in dev).

---

## Alternatives Considered

- Winston
- Bunyan
- Plain `console.log`

---

## References

https://github.com/pinojs/pino
https://github.com/iamolegga/nestjs-pino
