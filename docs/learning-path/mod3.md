# Module 3 — Core Operational Plugins

## Purpose

This module introduces the **core operational plugins** that staff interact with during
day-to-day server operations.

These plugins are considered **core** because:

- They affect player access or safety
- They are involved in most incidents or questions
- Misuse can cause widespread impact

This module focuses on **what each plugin owns**, not how to reconfigure it.

## What counts as a core operational plugin

A plugin is considered *core operational* if:

- It affects who can play
- It affects how players move between systems
- It affects moderation or safety
- Staff interact with it during incidents

Plugins that add cosmetics, QoL, or gameplay features are **reference-only**
and documented elsewhere.

## PlayerInitialization

### What it owns
- New player onboarding
- PlayerInit world behavior
- Verification polling loop
- Automated teleport after approval
- Triggering LuckPerms promotion

### What it does NOT own
- Email approval decisions
- Permission structure
- Staff authority

## LuckPerms

### What it owns
- Group membership
- Permission enforcement
- MAIN / ERRSA / STAFF track separation

### What it does NOT own
- Player verification
- Organizational identity decisions
- Manual promotion for access

## Floodgate & Geyser

### What they own
- Bedrock → Java protocol translation
- Username formatting (`.` prefix)
- Cross-platform compatibility

### What they do NOT own
- Permissions logic
- Verification decisions
- Server routing

## Velocity

### What it owns
- Entry point for all connections
- Routing players to servers
- Server separation and isolation

### What it does NOT own
- World management
- Permissions
- Plugin behavior inside servers

## Core vs reference plugins

Plugins are classified based on **impact**, not importance.

### Core plugins
Core plugins are systems that:

- Control player access, identity, or authority
- Affect multiple players or the entire server
- Are involved in onboarding, moderation, or recovery
- Can cause widespread disruption if misconfigured

Because of this:

- Core plugins are covered in training modules
- Core plugin changes must be documented in the server changelog
- Issues involving core plugins are escalated

### Reference plugins
Reference plugins are systems that:

- Affect gameplay features or quality-of-life
- Impact individual players or small groups
- Do not control access, authority, or onboarding
- Can usually be disabled or adjusted without system-wide impact

Because of this:

- Reference plugins are documented for lookup
- Reference plugin changes must be documented in the server changelog
- Reading them is not required for training
- Changes are lower-risk and more localized

## This module does not authorize

- Editing configs
- Reloading plugins
- Using LuckPerms editor
- Modifying Velocity routing
- Manual player promotion

## Module 3 completion check

You have completed this module if you can:

- Name the four core operational plugins
- Explain what each core plugin owns
- Identify which plugin a problem belongs to
- Know when escalation is required


---

## Next module

<div class="grid cards" markdown>

-   :rocket: **Module 4 — Change Control & Incident Response**  
    Learn how changes are made safely and how incidents are handled.  
    [:octicons-arrow-right-24: Start Module 4](../learning-path/mod4.md){ .md-button .md-button--primary }

</div>


