# Permissions Model

The ERRSA MC server uses **three parallel permission tracks** — not a single rank ladder.  
Each track answers a different question about a player.

- **MAIN:** Can the player interact with gameplay?
- **ERRSA:** Who is the player within ERRSA?
- **STAFF:** What authority does the player have?

!!! info "Key Rule"
    **Permission tracks are parallel, not hierarchical.**  
    Membership in one track never implies power in another.

---

## Visual Overview

!!! note "How to read this diagram"
    These are **parallel lanes**, not inheritance chains.  
    VIP (`premium`) is a cosmetic overlay and does **not** move someone toward staff authority.

    ```text
    ┌──────────────────────────┐   ┌──────────────────────────┐   ┌──────────────────────────┐
    │ MAIN — Player Lifecycle  │   │ ERRSA — Identity         │   │ STAFF — Authority         │
    ├──────────────────────────┤   ├──────────────────────────┤   ├──────────────────────────┤
    │ default  (unverified)    │   │ errsa                    │   │ mod                        │
    │ user     (verified)      │   │ hallrep                  │   │ admin                      │
    │ premium  (VIP cosmetic)  │   │ legacy                   │   │ dev                        │
    │                          │   │ execcoord                │   │                            │
    │                          │   │ execboard                │   │                            │
    │                          │   │ advisor                  │   │                            │
    └──────────────────────────┘   └──────────────────────────┘   └──────────────────────────┘
    ```
---

## MAIN Track — Player Lifecycle

Controls **when** a player can interact with gameplay.

### `default` — Unverified
- First join / unverified
- Isolated (void)
- Email verification only
- ❌ No gameplay access

### `user` — Verified Player
- Full survival gameplay
- Economy, claims, warps, voice chat

### `premium` — VIP Cosmetic Overlay
- Prefixes, QoL, cosmetics
- ✅ Cosmetic-only benefits
- ❌ **Never grants authority**

!!! warning "MAIN Track Boundary"
    MAIN determines **play state**, not staff power.  
    VIP status does **not** grant moderation or admin abilities.

---

## ERRSA Track — Organization & Identity

Controls **who someone is within ERRSA**.

### Groups
- `errsa`
- `hallrep`
- `legacy`
- `execcoord`
- `execboard`
- `advisor`

### Purpose
- Prefixes and recognition
- Organizational identity only

!!! danger "Hard Boundary"
    ERRSA identity groups **never** grant moderation, admin, or developer permissions.

---

## STAFF Track — Authority

Controls **actions that affect other players or the server**.

### `mod` — Moderation
- Enforce rules
- Mute / kick / ban
- Investigate players
- View logs, alerts, socialspy

**Does NOT grant:**

- ❌ Rollbacks or fixes
- ❌ Claim overrides
- ❌ Operator (OP)

---

### `admin` — Operations
- Rollbacks and damage restoration
- Claim and protection overrides
- Incident resolution
- Staff coordination

**Does NOT grant:**

- ❌ Plugin installation
- ❌ Config editing
- ❌ LuckPerms modification
- ❌ Operator (OP)

*Admins support devs but do not replace them.*

---

### `dev` — Technical Authority
- Full system access (`*`)
- Plugins and configs
- Permissions architecture
- Backend and stability

!!! note "Operator Access"
    **Only devs receive operator commands.**

!!! tip "Change Control"
    - Coordinate impactful changes with Admins
    - Follow backup procedures
    - Document all technical changes

---


<div class="center-table">

!!! note "Escalation Flow"

    | Situation | Escalate To |
    |----------|-------------|
    | Player behavior issue | `mod` |
    | Damage or incident | `admin` |
    | Plugins / configs / permissions | `dev` |

</div>

!!! warning "If Unsure"
    - Escalate upward
    - Document the issue
    - Never self-assign permissions

---

_Last reviewed: 2025-12-30_
