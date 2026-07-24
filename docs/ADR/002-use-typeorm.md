# ADR-002

## Title

Use TypeORM as the ORM.

---

## Status

Accepted

---

## Context

The project requires an ORM tightly integrated with NestJS.

The solution should support migrations, repositories and decorators while keeping the development experience familiar.

---

## Decision

TypeORM will be the default ORM.

---

## Consequences

### Positive

- Mature ecosystem.
- Official NestJS integration.
- Entity-based approach.
- Familiar API.
- Good migration support.

### Negative

- Less strict typing than Prisma.
- Some APIs feel more verbose.

---

## Alternatives Considered

- Prisma
- Sequelize
- MikroORM

---

## References

https://typeorm.io/
