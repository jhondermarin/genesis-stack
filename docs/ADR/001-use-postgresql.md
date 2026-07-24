# ADR-001

## Title

Use PostgreSQL as the primary relational database.

---

## Status

Accepted

---

## Context

Genesis Stack requires a relational database that is reliable, scalable and well supported by modern backend frameworks.

The database should be suitable for both small personal projects and larger production applications.

---

## Decision

PostgreSQL has been selected as the default relational database.

---

## Consequences

### Positive

- Excellent SQL compliance.
- Strong support for JSON data.
- Reliable transactions.
- Great ecosystem.
- Excellent Docker support.
- Works perfectly with TypeORM.

### Negative

- Slightly steeper learning curve than MySQL.
- Some hosting providers prioritize MySQL.

---

## Alternatives Considered

- MySQL
- MariaDB
- SQLite

---

## References

https://www.postgresql.org/
