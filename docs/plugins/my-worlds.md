# Multiverse-Core

## Purpose

**Category:** `Infrastructure`

Multiverse-Core manages multiple worlds on ERRSA MC, including world loading, world-specific gameplay rules, respawn behavior, teleport handling, and per-world environment settings. On ERRSA MC, it is used to maintain the main survival worlds as well as controlled-purpose worlds like `Lobby`, `PlayerInit`, and `LegacyLake`. :contentReference[oaicite:3]{index=3}

---

## Dependencies

!!! info "Required for this plugin to function"
- **Server:** Paper / Spigot
- **Plugins:**
  - `Multiverse-Core`
- **External services (if any):**
  - `None required for current ERRSA MC usage`

---

## Permissions Model

!!! note "Permissions are intentionally scoped"
    This plugin follows the **parallel permission track model**.  
    Access is granted by role, not convenience.

### Player permissions
- No direct Multiverse-Core access is granted to normal players on ERRSA MC

### Mod permissions
- No mod-level Multiverse-Core access is currently assigned

### Admin permissions
- No routine admin access is currently assigned

### Dev permissions
- Multiverse-Core access is restricted to **dev/trusted infrastructure staff only**

!!! warning
    World creation, import, teleport routing, and respawn configuration can affect the entire server.  
    Treat Multiverse-Core as a restricted infrastructure tool.

---

## Common Commands

!!! note "Only commands relevant to ERRSA workflows are listed"

### Player commands
- None

### Mod commands
- None

### Admin commands
- None routinely assigned on ERRSA MC

### Dev commands
- `/mv list` — list imported worlds
- `/mv info <world>` — inspect a world's Multiverse settings
- `/mv tp <world>` — teleport to a world
- `/mv spawn <world>` — teleport to a world spawn
- `/mv import <world>` — import an existing world
- `/mv create <world>` — create a world
- `/mv delete <world>` — remove a world from Multiverse / delete world if intended
- `/mv modify set <property> <value> <world>` — change world properties
- `/mv reload` — reload Multiverse config

---

## Configuration Files

!!! info "Primary config locations"
- `plugins/Multiverse-Core/config.yml`
- `plugins/Multiverse-Core/worlds.yml`
- `plugins/Multiverse-Core/anchors.yml`

### File roles
- `config.yml` — global Multiverse behavior, teleport rules, respawn handling, command safeguards
- `worlds.yml` — per-world settings such as gamemode, difficulty, PvP, spawn flags, and respawn behavior
- `anchors.yml` — saved anchors; currently empty on ERRSA MC

---

## ERRSA Defaults & Settings

!!! note "ERRSA-specific configuration choices"

### Global world behavior
- `auto-import-default-worlds: true`
- `auto-import-3rd-party-worlds: true`
- `enforce-access: false`
- `enforce-gamemode: true`
- `enforce-flight: true`
- `auto-purge-entities: false` :contentReference[oaicite:4]{index=4}

### Teleport behavior
- `use-finer-teleport-permissions: true`
- `teleport-intercept: true`
- `passenger-mode: default`
- `concurrent-teleport-limit: 50`
- safe-location search radius:
  - horizontal: `3`
  - vertical: `3` :contentReference[oaicite:5]{index=5}

### Spawn / respawn behavior
- `first-spawn-override: false`
- `enable-join-destination: false`
- `default-respawn-in-overworld: true`
- `default-respawn-within-same-world: true`
- `enforce-respawn-at-world-spawn: true` :contentReference[oaicite:6]{index=6}

### Portal and messaging behavior
- `use-custom-portal-search: false`
- `enable-chat-prefix: false`
- `register-papi-hook: true`
- `default-locale: en`
- `per-player-locale: true` :contentReference[oaicite:7]{index=7}

### Command safety
- `resolve-alias-name: true`
- `confirm-mode: enable`
- `use-confirm-otp: true`
- `confirm-timeout: 30`
- `show-legacy-aliases: false` :contentReference[oaicite:8]{index=8}

### Event priorities / debug
- `player-portal: high`
- `player-respawn: low`
- `player-spawn-location: normal`
- `player-teleport: highest`
- `global-debug: 0`
- `debug-permissions: false`
- `silent-start: false` :contentReference[oaicite:9]{index=9}

---

## Imported Worlds on ERRSA MC

### Main survival stack
- `world` — survival, hard difficulty, PvP enabled, hunger enabled, spawn memory kept, portals allowed
- `world_nether` — survival nether, hard difficulty, PvP enabled, scale `8.0`
- `world_the_end` — survival end, hard difficulty, PvP enabled, scale `16.0` :contentReference[oaicite:10]{index=10}

### Controlled / custom worlds
- `Lobby` — adventure mode, PvP off, monsters/animals/misc spawning disabled, weather allowed, keep spawn in memory enabled
- `PlayerInit` — adventure mode, peaceful, hunger off, PvP off, respawn-world set to `PlayerInit`
- `LegacyLake` — adventure mode, peaceful, hunger off, PvP off, weather off, keep spawn in memory disabled :contentReference[oaicite:11]{index=11}

### Anchors
- `anchors.yml` is currently empty: `anchors: {}`. :contentReference[oaicite:12]{index=12}

---

## ERRSA Design Intent

!!! note "Why these settings exist"

- Multiverse is being used as a **world governance layer**, not as a general player utility plugin
- Main worlds preserve normal survival gameplay
- Purpose-built worlds like `Lobby`, `PlayerInit`, and `LegacyLake` are locked down with adventure mode, low/no hostile pressure, and reduced survival mechanics
- Join-spawn override is disabled globally, so Multiverse is not forcing all login routing by itself
- Respawn logic is conservative and world-aware, with overworld fallback enabled and respawn-at-world-spawn enforced globally unless world properties override it :contentReference[oaicite:13]{index=13} :contentReference[oaicite:14]{index=14}

---

## Common Issues & Fixes

### Issue: Player enters a world and their gamemode changes unexpectedly

**Likely cause:** `enforce-gamemode: true` is enabled globally, and the destination world has a different configured gamemode. :contentReference[oaicite:15]{index=15}

**Fix:**  
- Check the target world's `gamemode` in `worlds.yml`
- Confirm the behavior is intended for that world

**Escalate if:** A gameplay world is forcing the wrong mode for all users unexpectedly

---

### Issue: Player cannot use beds/anchors the way expected in a custom world

**Likely cause:** The world-specific `bed-respawn` or `anchor-respawn` flags differ by world. For example, `Lobby` allows both, while `PlayerInit` and `LegacyLake` disable both. :contentReference[oaicite:16]{index=16}

**Fix:**  
- Check the affected world's respawn flags in `worlds.yml`
- Verify whether the world is intended to act as a controlled experience space

**Escalate if:** Respawn behavior conflicts with the design purpose of the world

---

### Issue: Player respawns somewhere unexpected

**Likely cause:** Global respawn rules are active, including `default-respawn-in-overworld: true`, `default-respawn-within-same-world: true`, and `enforce-respawn-at-world-spawn: true`, combined with any world-specific `respawn-world` value. `PlayerInit`, for example, explicitly sets `respawn-world: PlayerInit`. :contentReference[oaicite:17]{index=17} :contentReference[oaicite:18]{index=18}

**Fix:**  
- Check the world the player died in
- Review that world's `respawn-world`
- Review bed/anchor settings for that world

**Escalate if:** Respawns are inconsistent within the same world and not explained by config

---

### Issue: A world is loaded but behaves too “open” for access control

**Likely cause:** `enforce-access: false` is globally enabled, so Multiverse is not using world access permission gates. :contentReference[oaicite:19]{index=19}

**Fix:**  
- Restrict access operationally through other plugins/workflows
- Do not assume Multiverse itself is blocking entry

**Escalate if:** A restricted-use world needs permission-gated entry in production

---

### Issue: `/mv` dangerous actions require confirmation

**Likely cause:** `confirm-mode: enable` and `use-confirm-otp: true` are active. :contentReference[oaicite:20]{index=20}

**Fix:**  
- Complete the `/mv confirm` flow with the provided code
- This is expected and should not be disabled casually

**Escalate if:** Trusted dev workflows are being blocked in error

---

## Notes for ERRSA MC Maintainers

!!! warning "Restricted infrastructure plugin"
    Multiverse-Core should remain a **dev-only operational tool** on ERRSA MC.

### Key operational notes
- Access is intentionally limited to dev/trusted infrastructure staff
- World behavior is split clearly between:
  - survival worlds (`world`, `world_nether`, `world_the_end`)
  - controlled experience worlds (`Lobby`, `PlayerInit`, `LegacyLake`) :contentReference[oaicite:21]{index=21}

### Important settings to remember
- `enforce-access: false`
- `enforce-gamemode: true`
- `teleport-intercept: true`
- `default-respawn-in-overworld: true`
- `enforce-respawn-at-world-spawn: true`
- `confirm-mode: enable`
- `use-confirm-otp: true` :contentReference[oaicite:22]{index=22} :contentReference[oaicite:23]{index=23} :contentReference[oaicite:24]{index=24}

### Anchors note
- `anchors.yml` is currently empty, so no saved Multiverse anchors are in use right now. :contentReference[oaicite:25]{index=25}

---

_Last verified: 2026-03-20_  
_Server version: 1.21.4_
