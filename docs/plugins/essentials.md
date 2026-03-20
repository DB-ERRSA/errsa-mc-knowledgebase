# EssentialsX

## Purpose

**Category:** `Core / Economy / Utility`

EssentialsX is the **primary core plugin** on ERRSA MC, handling:

- Player commands (teleport, homes, messaging)
- Economy system (balance, pay, server shop integration)
- Moderation tools (kick, mute, jail)
- Server information (rules, motd, info pages)

---

## Dependencies

!!! info "Required for this plugin to function"
- **Server:** Paper
- **Plugins:**
  - `Vault` (economy integration)
  - `LuckPerms` (permissions)
  - `EssentialsChat` (chat formatting)


---

## Permissions Model

!!! note "Permissions are intentionally scoped"
    This plugin follows the **parallel permission track model**.  
    Access is granted by role, not convenience.

---

### Player permissions
- `essentials.spawn` — teleport to spawn  
- `essentials.home` — set and use homes  
- `essentials.tpa` / `tpaccept` — teleport requests  
- `essentials.msg` — private messaging  
- `essentials.pay` — send money  
- `essentials.balance` — view balance  
- `essentials.rules` — view server rules  
- `essentials.motd` — view MOTD  
- `essentials.info` — view server info  
- `essentials.warp` — use warps  


---

### Mod permissions
- `essentials.kick` — remove players  
- `essentials.mute` — mute players  
- `essentials.tempban` — temporary bans  
- `essentials.jail` — jail players  
- `essentials.socialspy` — monitor messages  
- `essentials.invsee` — view inventories  
- `essentials.near` — find nearby players  
- `essentials.seen` — lookup player activity  


---

### Admin permissions
- `essentials.gamemode` — change gamemode  
- `essentials.fly` — enable flight  
- `essentials.give` — spawn items  
- `essentials.eco` — manage economy  
- `essentials.setspawn` — set spawn  
- `essentials.setwarp` — manage warps  
- `essentials.enchant` — apply enchantments  
- `essentials.item` — spawn items  
- `essentials.exp.*` — manage XP  

---

### Dev permissions
- Full access to all `essentials.*` nodes  
- Used for debugging, economy tuning, and system testing  

---

## Common Commands

!!! note "Only commands relevant to ERRSA workflows are listed"

### Player commands
- `/spawn` — return to spawn  
- `/home` — teleport home  
- `/tpa <player>` — request teleport  
- `/pay <player> <amount>` — send money  
- `/bal` — check balance  
- `/rules` — view rules  


---

### Mod commands
- `/kick <player>` — remove player  
- `/mute <player>` — mute player  
- `/jail <player>` — jail player  
- `/invsee <player>` — inspect inventory  

---

### Admin commands
- `/gamemode <mode>` — change gamemode  
- `/fly` — toggle flight  
- `/give <item>` — give items  
- `/eco give/take` — manage economy  
- `/setspawn` — set spawn  

---

### Dev commands
- `/ess reload` — reload config  
- `/eco reset` — reset balances  
- `/setworth` — modify item values  

---

## Configuration Files

!!! info "Primary config locations"
- `plugins/Essentials/config.yml`
- `plugins/Essentials/worth.yml`
- `plugins/Essentials/kits.yml`
- `plugins/Essentials/spawn.yml`
- `plugins/Essentials/tpr.yml`
- `plugins/Essentials/jail.yml`
- `plugins/Essentials/messages/`
- `plugins/Essentials/userdata/`

---
