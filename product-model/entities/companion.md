---
kind: system
acts: external
relations:
- entity: task
  verb: manages
  cardinality: one-to-many
- entity: appliance
  verb: manages
  cardinality: one-to-many
---

# Companion

Another Home Assistant integration that works with Home Keeper: it registers itself, contributes and manages its own tasks and appliances, and arms and clears condition-driven tasks.

## Information kept

- **Name** — the name shown in Settings → Companions
- **Integration** — the Home Assistant integration domain of the companion
- **Configure link** — the companion's own configuration page
- **Panel tab** — a tab the companion adds to the panel, if any
