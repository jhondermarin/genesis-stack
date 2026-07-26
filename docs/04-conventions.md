# Coding Conventions

## General

- Write code in English.
- Keep functions small.
- Prefer readability over cleverness.
- Avoid duplicated code.
- Use meaningful names.

---

# Naming

## Variables

Good

```ts
const totalPrice
const currentUser
const housePlanner
```

Bad

```ts
const tp
const usr
const hp
```

---

## Functions

Good

```ts
calculateTotal()
findUserById()
createInvoice()
```

---

## Components

Use PascalCase.

```
UserCard.tsx
DashboardCard.tsx
Sidebar.tsx
```

---

## Hooks

Always begin with "use".

```
useAuth.ts

useTheme.ts

useUsers.ts
```

---

## Interfaces

Do not prefix with I.

Good

```ts
interface User
```

Bad

```ts
interface IUser
```

---

## Enums

Use PascalCase.

```ts
enum UserRole
```

---

# Folder Naming

Folders use lowercase.

```
users

auth

dashboard
```

---

# File Naming

Components

```
UserCard.tsx
```

Utilities

```
date.utils.ts
```

Services

```
users.service.ts
```

Controllers

```
users.controller.ts
```

Entities

```
user.entity.ts
```

DTOs

```
create-user.dto.ts
```

---

# Git

Branches

```
main

develop

feature/auth

feature/dashboard

fix/login

hotfix/security
```

Commits follow Conventional Commits.

Examples

```
feat: add authentication module

fix: resolve login validation

docs: update architecture

refactor: simplify user service

test: add auth unit tests
```

---

# Code Style

- One responsibility per function.
- Early return whenever possible.
- Avoid nested conditionals.
- Prefer composition over inheritance.
- Keep controllers thin.
- Keep business logic inside services.
- Extract reusable code.

---

# Environment Variables

Every app defines a Zod schema describing its expected environment variables.

`process.env` is parsed against that schema at bootstrap; the app fails fast with a clear error if a variable is missing or malformed.

New variables must be added to both the schema and `.env.example` in the same change.

See ADR-007.

---

# Documentation

Every important architectural decision must be documented through ADRs.

Code should explain **how**.

Documentation should explain **why**.
