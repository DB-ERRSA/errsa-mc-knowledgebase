# Permissions Model

The ERRSA MC server uses **three parallel permission tracks**.  
Each track answers a different question about a player.

---

## Visual overview

```text
MAIN (Player Lifecycle)      ERRSA (Identity)           STAFF (Authority)
──────────────────────      ────────────────────      ───────────────────
default                     errsa                     mod
  │                          │                         │
  ▼                          ▼                         ▼
user                        hallrep                  admin
  │                          │                         │
  ▼                          ▼                         ▼
premium (VIP)               legacy                   dev
                             │
                             ▼
                          execcoord
                             │
                             ▼
                          execboard
                             │
                             ▼
                           advisor
```

- Coordinate changes with Admins
- Follow backup procedures
- Document all technical changes

!!! info "MAIN track — Player lifecycle"
Controls when a player can interact with the server
**`default`**
- First join / unverified
- Player isolated (void)
- Email verification only
- No gameplay access

**`user`**
- Verified player
- Full survival gameplay
- Economy, claims, warps, voice chat

**`premium` (VIP)**
- Optional cosmetic overlay
- Prefixes, QoL, cosmetics
- **Never grants authority**

!!! note "ERRSA track — Organization & identity"
Controls who someone is within ERRSA

Groups:

- `errsa`
- `hallrep`
- `legacy`
- `execcoord`
- `execboard`
- `advisor`

Purpose:
- Prefixes & recognition
- Organizational identity

!!! danger
    ERRSA membership **never** grants moderation, admin, or dev permissions.

!!! warning "STAFF track — Authority"
Controls what actions affect other players or the server
**`mod` — Moderation**
- Enforce rules
- Mute / kick / ban
- Investigate players
- View logs & alerts  
🚫 Cannot fix damage • 🚫 Cannot override protections • 🚫 Not OP

**`admin` — Operations**
- Fix damage (rollbacks)
- Override claims & protections
- Resolve incidents
- Coordinate staff response  
🚫 Cannot install plugins • 🚫 Cannot edit configs • 🚫 Cannot modify LuckPerms • 🚫 **Admins are not OP**  
*Admins help devs with non-technical server management.*

**`dev` — Technical authority**
- Full system access (`*`)
- Plugins & configs
- Permissions structure
- Backend & stability

!!! danger
    Dev is **not** “Admin with more buttons”.

##Escalation Flow##
Player behavior issue?  → mod
Damage or incident?     → admin
System/plugin/config?   → dev

If you’re unsure:

- Escalate upward
- Document the issue
- Do not self-assign permissions

----
_Last reviewed: 2025-01

