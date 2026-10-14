---
appliesTo:
- type: entity
  id: part
  effect: changes
  facts:
  - Name
  - Part number
  - Vendor
  - Cost
  - Notes
  - Kind
  - Replacement interval
  - Action
  - Count uses as
  - Use task name
  - Target uses
  - Time limit
  - Reorder at
  - Stock unit
  - Used per completion
  - Restock quantity
  - Auto-create buy task
  - Product URL
  - Attached file
  - NFC tag
  - Require tag scan
permits:
- actors:
  - admin
  - automation
  - companion
references:
- kind: doc
  role: intent
  target: docs/SECURITY.md
- kind: doc
  role: intent
  target: docs/guide/start/household-users.md
---

# Only an admin edits a part

A household member cannot change a part's details, schedule, stock settings, file or tag; an admin, an automation or a companion can.

## Rationale

Appliances own Home Assistant devices, and Home Assistant reserves device changes for admins; Home Keeper gates the panel command and the service alike. A call that carries no person comes from an automation or another integration and is trusted, as Home Assistant trusts it.
