# Getting Started

This page orients new developers and administrators to the ERRSA Minecraft server.  
Read this fully before making **any** changes.

---

## Who this is for
- Incoming ERRSA MC admins
- Developers maintaining plugins, configs, or infrastructure
- Officers taking over server ownership or finances

If you are only moderating in-game, you likely do **not** need this page (helpful to know).

---

## System overview (high level)

- **Game server**: Minecraft (Paper)
- **Host**: Apex Hosting
- **Management panel**: Apex Panel
- **Database access**: phpMyAdmin (via Apex)
- **Permissions**: LuckPerms
- **Source of truth**: This knowledgebase

---

## Where things live

### Hosting
- **Provider**: Apex Hosting  
- **Access**: Admins, Developers, MC Lead, and ERRSA Exec
- **Primary responsibilities**:
  - Server uptime
  - File access
  - Backups
  - Database hosting

!!! tip
    Never share Apex credentials outside approved ERRSA admins.

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
  - Storing player emails
  - Handles external registration

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

## Golden rules (non-negotiable)

1. **No backup = no change**  
2. **Document every plugin or config change** in this wiki **AND** in the changelog (LINK HERE)
3. **Never give players permissions directly** — always use Luckyperm groups  
4. **Restart > reload** unless plugin docs explicitly say reload is safe  

Breaking these rules is how servers get corrupted.

---

## First-day checklist (new admin)

Complete these before touching production:

- [ ] Can log into Apex Hosting
- [ ] Can access File Manager or SFTP
- [ ] Can view LuckPerms groups
- [ ] Can locate server logs
- [ ] Has read the Permissions Model page
- [ ] Understands backup process

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
- Reloading plugins blindly
- Making undocumented changes
- “Just testing something real quick”

---

## Where to go next
- **Permissions** → How access control is structured  
- **Plugins** → Per-plugin documentation and update steps  
- **Troubleshooting** → What to do when things break  

---

_Last reviewed: 2025-01 | Applies to current ERRSA MC production server_
