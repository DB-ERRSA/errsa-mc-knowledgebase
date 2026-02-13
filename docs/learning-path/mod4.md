## Purpose

This module defines how changes are made safely and how incidents are handled
on the ERRSA Minecraft server.

Most server damage is not caused by malice — it is caused by **uncontrolled change**.
This module exists to prevent that.

## What counts as a change

A change is **anything** that alters server behavior, data, or player access, including:
- Editing plugin configs
- Updating or adding plugins
- Changing permissions or groups
- Reloading or restarting services
- Modifying databases
- Moving players between servers

## Approved change workflow

1. Confirm a **recent backup** exists
2. Define exactly what is being changed
3. Make the change
4. Restart the affected service
5. Verify expected behavior
6. Document the change in the wiki

## Backups

Backups are provided by the hosting provider and cover:
- World data
- Plugin configurations
- Player data

## Documentation requirements

Any change that affects server behavior must be documented:
- What changed
- Why it changed
- When it changed
- Who made the change

## Change vs incident

- **Change**
  - Planned
  - Controlled
  - Reversible

- **Incident**
  - Unplanned
  - Player-impacting
  - Requires stabilization before fixing
 
## Escalation matrix

- Player behavior or reports → Moderator
- System instability → Admin
- Plugin or backend failure → Developer
- Network or data risk → Committee Lead

## After an incident

Once stability is restored:
- Document the incident
- Identify root cause
- Update documentation if needed
- Adjust procedures to prevent recurrence

## Module 4 completion check

You have completed this module if you can:
- Define what counts as a change
- Follow the approved change workflow
- Distinguish an incident from a planned change
- Know when to escalate instead of acting

## Completion

Modules 1–4 establish the **baseline operational knowledge**
required to safely participate in ERRSA MC server administration.

Advanced topics and specialization follow from here.




