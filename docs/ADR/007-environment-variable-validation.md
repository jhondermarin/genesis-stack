# ADR-007

## Title

Validate environment variables with Zod at startup.

---

## Status

Accepted

---

## Context

Both apps read configuration from environment variables (database credentials, JWT secret, Redis host, API URLs).

Without validation, a missing or malformed variable fails silently or crashes deep inside the application instead of at startup, making the root cause hard to trace.

Zod is already part of the stack, so it is a natural fit for this purpose.

---

## Decision

Each app defines a Zod schema describing its expected environment variables and parses `process.env` against it during application bootstrap. The application must fail fast with a clear error if validation fails.

---

## Consequences

### Positive

- Configuration errors are caught immediately at startup, not at runtime.
- The schema doubles as living documentation of required configuration.
- Type-safe access to environment variables throughout the app.

### Negative

- Adds a small amount of boilerplate per app.
- Schemas must be kept in sync with `.env.example`.

---

## Alternatives Considered

- No validation (rely on `.env.example` only)
- `envalid`
- `joi`

---

## References

https://zod.dev/
