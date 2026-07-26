# ADR-006

## Title

Use pnpm as package manager and Turborepo as monorepo build orchestrator.

---

## Status

Accepted

---

## Context

Genesis Stack is a monorepo with multiple apps and shared packages.

Without a defined package manager and build orchestrator, dependency installation, caching and task execution across `apps/` and `packages/` would be handled inconsistently across projects.

---

## Decision

The project will use pnpm workspaces for dependency management and Turborepo for task orchestration (build, lint, test, dev) across the monorepo.

---

## Consequences

### Positive

- Disk-efficient installs via pnpm's content-addressable store.
- Strict dependency resolution (no phantom dependencies).
- Remote and local caching of tasks through Turborepo.
- Parallel execution of tasks across apps and packages.

### Negative

- Additional configuration files (`pnpm-workspace.yaml`, `turbo.json`).
- Contributors must be familiar with pnpm-specific behavior (strict node_modules).

---

## Alternatives Considered

- npm workspaces
- Yarn workspaces
- Nx

---

## References

https://pnpm.io/workspaces
https://turbo.build/repo/docs
