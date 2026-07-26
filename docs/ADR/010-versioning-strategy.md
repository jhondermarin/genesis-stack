# ADR-010

## Title

Version Genesis Stack itself using Semantic Versioning.

---

## Status

Accepted

---

## Context

Genesis Stack is a living methodology that evolves through versions (v0.1 Foundation, v0.2 Infrastructure, ...). Without an explicit versioning strategy, it is unclear how a project already built on an earlier version should adopt changes introduced later, or what level of change to expect from a version bump.

---

## Decision

Genesis Stack follows Semantic Versioning (`MAJOR.MINOR.PATCH`):

- **MAJOR**: breaking changes to architecture or conventions that require manual migration in existing projects.
- **MINOR**: new capabilities added in a backward-compatible way (e.g. a new roadmap milestone completed).
- **PATCH**: documentation fixes, clarifications or non-breaking corrections.

Each release is documented in `docs/05-roadmap.md`, and any change affecting existing projects is accompanied by a migration note in the corresponding ADR.

A `vX.Y.0` tag marks the completion of a full roadmap phase (e.g. Foundation, Infrastructure, Backend). A `vX.Y.Z` tag (Z > 0) marks reinforcements, corrections or documentation additions made within that same phase, without starting a new one.

---

## Consequences

### Positive

- Clear expectations of impact when the stack version changes.
- Existing projects can decide when and how to adopt a new version instead of drifting silently.

### Negative

- Requires discipline to document migration notes for breaking changes.

---

## Alternatives Considered

- Unversioned, continuous rolling changes (rejected: no way to track what a given project was built against).

---

## References

https://semver.org/
