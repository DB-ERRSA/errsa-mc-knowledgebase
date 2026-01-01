# Getting Started

How the ERRSA MC server is structured, where systems live, and how changes are made safely.
!!! info "You are **not** expected to memorize this page"
  You are expected to know where answers live and when to escalate
---

## Purpose
This page orients new ERRSA MC committee members, admins, and developers to how the server is built and operated. It provides a high-level overview of systems, access, and workflows before any technical changes are made.

---

## Who this is for

- Incoming ERRSA MC committee members
- Admins and Developers assuming operational responsibility


## Who can skip most of this

- Moderators acting only in-game
- Staff not responsible for server configuration
---

## System overview (high level)

- **Game server:** Minecraft (Paper)
- **Hosting provider:** Apex Hosting
- **Management panel:** Apex Panel
- **Database:** MySQL (via phpMyAdmin)
- **Permissions:** LuckPerms
- **Source of truth:** This wiki


---

## Hosting Operations

- **Access**: Admins, Developers, MC Lead, and ERRSA Exec
  
- **Primary responsibilities**:
  - Server uptime
  - File access
  - Backups
  - Database hosting


---

### Server files
Accessible through the Apex Panel → **File Manager** or **FTP File Access**.

Common locations:

- `/plugins/` — all plugin `.jar` files
- `/plugins/<PluginName>/` — plugin configs and data
- `/logs/` — crash reports and runtime logs
- `/world*/` — world data (do **not** edit casually)

---

### Database
- **Tool**: phpMyAdmin (via Apex)
- **Used for**:
  - Player initialization
  - Email verification
  - External registration systems

!!! warning
    Never manually edit database tables unless the plugin documentation explicitly says it is safe.

---

### Backups
- **Provided by**: Apex Hosting
- **Cadence**: (document exact schedule here)
- **Scope**:
  - World files
  - Plugin configs
  - Player data

!!! danger
    Never update plugins or configs without a recent backup.

---

## Golden rules

1. **No backup = no change**  
2. **Document every plugin or config change** in this wiki **AND** in the changelog (LINK HERE)
3. **Never give players permissions directly** — use Luckyperm groups  

Breaking these rules is how servers get corrupted.

---


## How changes should be made

### Safe workflow
1. Confirm a recent backup exists
2. Make the change
3. Restart the server
4. Verify functionality
5. Update documentation

### Unsafe workflow (do not do this)
- Editing live configs without backup
- Reloading plugins blindly (never reload)
- Making undocumented changes

---

## Where to go next
- **Learning Path** — Guided modules from beginner to trusted operator
- **Permissions Model** — How access and authority are structured
- **Plugins** — Per-plugin documentation and behavior

---

_Last reviewed: 2025-12-30 | Applies to current ERRSA MC production server_
