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

!!! note "Interactive Permissions Model"
    Hover over each role to see what it means and what it **does not** imply.

 <div class="permissions-visual">
      <section class="role-grid" aria-label="Server roles overview">
        <!-- MAIN -->
        <article class="role-card">
          <header class="role-head">
            <div class="role-kicker">MAIN</div>
            <h3 class="role-title">Player Lifecycle</h3>
          </header>
          <ul class="role-list">
            <li class="hover" data-tip="Unverified player. Limited access until email verification is completed.">
              <span class="role-name">default</span>
              <span class="role-note">unverified</span>
            </li>
            <li class="hover" data-tip="Verified player with standard access to the server.">
              <span class="role-name">user</span>
              <span class="role-note">verified</span>
            </li>
            <li class="hover" data-tip="Optional cosmetic rank purchased by the user. Cosmetic-only benefits; no gameplay/staff authority.">
              <span class="role-name">premium</span>
              <span class="role-note">VIP cosmetic</span>
            </li>
          </ul>
        </article>
        <!-- ERRSA -->
        <article class="role-card">
          <header class="role-head">
            <div class="role-kicker">ERRSA</div>
            <h3 class="role-title">Identity</h3>
          </header>
          <div class="chip-wrap" role="list" aria-label="ERRSA identity roles">
            <span class="chip" role="listitem" data-tip="General member of the Embry-Riddle Resident Student Association.">errsa</span>
            <span class="chip" role="listitem" data-tip="Hall Representative serving a specific residence hall.">hallrep</span>
            <span class="chip" role="listitem" data-tip="Former Executive Board member. Recognition role.">legacy</span>
            <span class="chip" role="listitem" data-tip="Executive Coordinator assisting ERRSA operations and initiatives.">execcoord</span>
            <span class="chip" role="listitem" data-tip="Current Executive Board member with organizational leadership duties.">execboard</span>
            <span class="chip" role="listitem" data-tip="Official ERRSA advisor providing oversight and guidance.">advisor</span>
          </div>
          <p class="role-footnote">
            Identity roles describe your relationship to ERRSA (not staff authority).
          </p>
        </article>
        <!-- STAFF -->
        <article class="role-card">
          <header class="role-head">
            <div class="role-kicker">STAFF</div>
            <h3 class="role-title">Authority</h3>
          </header>
          <ul class="role-list">
            <li class="hover" data-tip="Moderation staff responsible for enforcing server rules.">
              <span class="role-name">mod</span>
            </li>
            <li class="hover" data-tip="Administrative staff with elevated permissions and incident-resolution authority.">
              <span class="role-name">admin</span>
            </li>
            <li class="hover" data-tip="Development staff responsible for plugins, configs, systems, and permissions architecture.">
              <span class="role-name">dev</span>
            </li>
          </ul>
        </article>
      </section>
    </div>

  
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


!!! note "Escalation Flow"

    | Situation | Escalate To |
    |----------|-------------|
    | Player behavior issue | `mod` |
    | Damage or incident | `admin` |
    | Plugins / configs / permissions | `dev` |


!!! warning "If Unsure"
    - Escalate upward
    - Document the issue
    - Never self-assign permissions

---

_Last reviewed: 2025-12-30_
