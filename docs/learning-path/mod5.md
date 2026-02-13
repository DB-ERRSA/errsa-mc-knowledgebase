# Module 5 — Advanced  Systems & Developer Responsibility

## Purpose

This module covers advanced systems that directly affect server integrity,
data consistency, and long-term maintainability.

Access to these systems is granted by **trust**, not by completing modules.

This module exists to prevent irreversible damage.

## Advanced systems

Advanced systems are any components that:

- Persist data outside the game world
- Affect multiple servers at once
- Cannot be safely “undone” in minutes
- Can silently corrupt data if misused

## Databases & persistent data

The server uses external databases to store:

- Player registration state
- Email verification status
- Cross-session identifiers

## Permissions architecture

Permissions are a **designed system**, not a convenience tool.

## Network-level control

Velocity is the control plane for:

- Entry points
- Server isolation
- Cross-server movement

## Plugin internals

Plugins are not black boxes — but they are not playgrounds.

## Automation & scripts

Automation increases impact — both good and bad.

## Environment separation

- **Survival** — live players, real data
- **Test** — experimentation, validation

## Developer responsibility

Developers are responsible not only for changes,
but for the *future consequences* of those changes.

## Module 5 completion check

You have completed this module if you:

- Treat access as responsibility, not privilege
- Understand why restraint matters
- Know when to escalate instead of acting
- Can explain long-term risk, not just short-term fixes

## Completion

Modules 1–5 define the complete operational and technical
training path for ERRSA MC server leadership.

From this point forward, learning is situational, documented,
and responsibility-driven.


---
_Last reviewed: 2025-02-13 | Applies to current ERRSA MC server network_



