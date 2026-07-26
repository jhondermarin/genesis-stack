# ADR-009

## Title

Define a minimum security baseline for every backend application.

---

## Status

Accepted

---

## Context

JWT is already chosen for authentication (see tech stack), but authentication alone does not cover basic HTTP hardening. Without a defined baseline, each project could ship with a different — or absent — level of protection against common attacks.

---

## Decision

Every NestJS backend must enable, from the first commit:

- `helmet` for secure HTTP headers.
- A restrictive, explicit CORS configuration (no wildcard origins in production).
- Global rate limiting via `@nestjs/throttler`.
- Global input validation (`class-validator` / `ValidationPipe`) rejecting unknown properties.

---

## Consequences

### Positive

- Consistent baseline protection across all projects without extra decisions per project.
- Reduces exposure to common OWASP-listed HTTP vulnerabilities out of the box.

### Negative

- Slightly stricter defaults may require explicit configuration when integrating new clients or origins.

---

## Alternatives Considered

- Deciding security configuration per project (rejected: inconsistent, easy to forget).

---

## References

https://docs.nestjs.com/security/helmet
https://docs.nestjs.com/security/rate-limiting
https://docs.nestjs.com/security/cors
