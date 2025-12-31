# <Plugin Name>

!!! abstract "Purpose"
    **Category:** <Gameplay / Moderation / Protection / Infrastructure / Cosmetics / Mapping>  
    <1–2 sentence plain-English description of what this plugin exists to do on ERRSA MC.>

---

## Dependencies

!!! info "Required for this plugin to function"
- **Server:** Paper / Spigot / Fabric (specify)
- **Plugins:**
  - `<Dependency 1>`
  - `<Dependency 2>`
- **External services (if any):**
  - `<e.g., database, web map, API>`

---

## Permissions Model

!!! note "Permissions are intentionally scoped"
    This plugin follows the **parallel permission track model**.  
    Access is granted by role, not convenience.

### Player permissions
- `<permission.node>` — what it allows

### Mod permissions
- `<permission.node>` — what it allows

### Admin permissions
- `<permission.node>` — what it allows

### Dev permissions
- `<permission.node>` — full control / maintenance

!!! danger "What this plugin does NOT grant"
    - ❌ Does not bypass claims or protections unless explicitly listed  
    - ❌ Does not grant moderation or admin authority outside its scope  
    - ❌ Does not imply OP access  

---

## Common Commands

!!! note "Only commands relevant to ERRSA workflows are listed"

### Player commands
- `/command <arg>` — description

### Mod commands
- `/command <arg>` — description

### Admin commands
- `/command <arg>` — description

### Dev commands
- `/command <arg>` — description

---

## Configuration Files

!!! info "Primary config locations"
- `plugins/<PluginName>/config.yml`
- `plugins/<PluginName>/settings.yml`
- `plugins/<PluginName>/data/` (if applicable)

!!! warning "Change control"
    Config changes should be coordinated with **Admins** and documented by **Devs**.

---

## ERRSA Defaults & Settings

!!! note "ERRSA-specific configuration choices"
- `<Setting>`: `<value>` — reason
- `<Setting>`: `<value>` — reason
- `<Feature disabled>` — why we disable it

This section documents **intentional deviations from plugin defaults**.

---

## Common Issues & Fixes

### Issue: <What someone reports>
**Likely cause:** <cause>  
**Fix:** <what the role can safely do>  
**Escalate if:** <conditions>

---

### Issue: <Another common problem>
**Likely cause:** <cause>  
**Fix:** <fix>  
**Escalate if:** <conditions>

---

## Escalation

| Situation | Escalate To |
|----------|-------------|
| Player misuse or confusion | `mod` |
| Damage, rollback, or override needed | `admin` |
| Plugin bug, config change, or update | `dev` |

!!! warning "Do not self-assign permissions"
    If access is missing, that is intentional.  
    Escalate instead of requesting temporary permissions.

---

_Last verified: 2025-01-XX_  
_Server version: 1.20.x_
