# Architecture

## Overview

Genesis Stack follows a modular architecture designed to maximize maintainability, scalability and code reuse.

Each application is independent but follows the same conventions and project structure.

The repository is organized as a monorepo, separating applications, shared resources and infrastructure.

---

# Repository Structure

```
genesis-stack/

├── apps/
│   ├── frontend/
│   └── backend/
│
├── docs/
│
├── docker/
│
├── scripts/
│
├── templates/
│
├── .env.example
├── docker-compose.yml
├── README.md
└── LICENSE
```

---

# Frontend Architecture

```
src/

├── app/
├── components/
├── features/
├── hooks/
├── lib/
├── services/
├── styles/
├── types/
└── utils/
```

## Responsibilities

### app/

Application routes using Next.js App Router.

### components/

Reusable UI components.

### features/

Feature-specific components, hooks and logic.

### hooks/

Reusable React hooks.

### services/

API communication.

### lib/

Third-party library configuration.

### utils/

Pure helper functions.

### types/

Shared TypeScript types.

---

# Backend Architecture

```
src/

├── common/
│
├── config/
│
├── database/
│
├── modules/
│
└── main.ts
```

## Responsibilities

### common/

Shared decorators, guards, interceptors, filters, pipes and utilities, including the Pino logging module (ADR-008) and the global security setup — Helmet, CORS and rate limiting (ADR-009).

### config/

Application configuration, including the Zod schema that validates `process.env` at bootstrap (`env.ts`). See ADR-007.

### database/

TypeORM configuration and migrations.

### modules/

Business modules.

Each module should contain:

```
users/

controllers/

services/

entities/

dto/

repositories/

interfaces/
```

---

# Design Principles

- Feature-first organization.
- Clear separation of responsibilities.
- Low coupling.
- High cohesion.
- Dependency Injection.
- Composition over inheritance.
- Shared code belongs in common/.
- Business logic never belongs in controllers.

---

# Future Evolution

The architecture should evolve without breaking consistency.

New technologies should integrate naturally into the existing structure instead of forcing architectural changes.
