# ADR-003

## Title

Use a monorepo structure.

---

## Status

Accepted

---

## Context

Genesis Stack contains multiple applications that share architecture, tooling and documentation.

Keeping everything in a single repository simplifies maintenance.

---

## Decision

The project will follow a monorepo structure.

---

## Consequences

### Positive

- Shared configuration.
- Easier dependency management.
- Consistent tooling.
- Shared documentation.

### Negative

- Larger repository.
- More complex CI/CD.

---

## Alternatives Considered

- Multiple repositories

---

## References

https://monorepo.tools/
