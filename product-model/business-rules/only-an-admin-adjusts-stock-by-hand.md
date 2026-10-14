---
appliesTo:
- type: entity
  id: part
  effect: changes
  facts:
  - Stock
  - Last replaced
  contexts:
  - {place: 'panel::household::appliance'}
  - {place: services}
permits:
- actors:
  - admin
  - automation
  - companion
- unattended: true
references:
- kind: doc
  role: intent
  target: docs/SECURITY.md
- kind: doc
  role: intent
  target: docs/guide/appliances/appliances.md
---

# Only an admin adjusts a part's stock by hand

On the appliance page and through the adjust part stock and update asset actions, only an admin, an automation or a companion moves a part's stock or last replaced date. A completion of a task that uses the part draws its stock, and a completed buy task restocks it, whoever completed the task.

## Rationale

Appliances own Home Assistant devices, and Home Assistant reserves device changes for admins; Home Keeper gates the panel command and the service alike. A call that carries no person comes from an automation or another integration and is trusted, as Home Assistant trusts it.
