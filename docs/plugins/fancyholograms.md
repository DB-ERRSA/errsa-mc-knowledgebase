# FancyHolograms

## Purpose

**Category:** `Cosmetics`  

FancyHolograms is used to create advanced floating holograms (text, items, and blocks) for navigation, NPC labeling, and immersive decoration across ERRSA MC.

---

## Common Commands

!!! note "Only commands relevant to ERRSA workflows are listed"

### Dev commands
- `/hologram create <name>` — create hologram  
- `/hologram edit <name>` — modify hologram  
- `/hologram delete <name>` — remove hologram  
- `/hologram movehere <name>` — reposition hologram  

---

## Configuration Files

!!! info "Primary config locations"
- `plugins/FancyHolograms/config.yml`
- `plugins/FancyHolograms/featureFlags.yml`
- `plugins/FancyHolograms/holograms.yml`
- `plugins/FancyHolograms/logs/`

---

## ERRSA Defaults & Settings

!!! note "ERRSA-specific configuration choices"

- `visibility_distance: 20` — reduces render load and improves performance :contentReference[oaicite:0]{index=0}  
- `autosave_interval: 15` — prevents data loss during edits :contentReference[oaicite:1]{index=1}  
- `disable-holograms-for-bedrock-players: false` — ensures cross-platform visibility :contentReference[oaicite:2]{index=2}  

### Implementation Notes
- Extensive use of **TEXT holograms for NPC labels and instructions** (e.g., “Sensei”, “Claim Points”) :contentReference[oaicite:3]{index=3}  
- Use of **ITEM holograms** (tools, dyes, weapons) to visually represent systems or shops :contentReference[oaicite:4]{index=4}  
- Use of **BLOCK holograms** for environmental decoration (doors, props, visual markers) :contentReference[oaicite:5]{index=5}  
- Many holograms are **linked to NPC systems** using `linkedNpc`, enabling interaction workflows :contentReference[oaicite:6]{index=6}  
- Custom scaling and positioning are heavily used for polished visual presentation  

---

_Last verified: 2026-02-13_  
_Server version: 1.21.4_
