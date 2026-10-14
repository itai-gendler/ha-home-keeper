---
appliesTo:
- type: entity
  id: declarative-companion
  effect: removes
permits:
- actors:
  - admin
  - automation
  - companion
references:
- kind: doc
  role: intent
  target: docs/SECURITY.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/__init__.py
---

# Only an admin deletes a declarative companion

A household member cannot delete declarative companions; an admin can, and so can an automation or a companion that calls with no person behind it.

## Rationale

Appliances own Home Assistant devices, and Home Assistant reserves device changes for admins; Home Keeper gates the panel command and the service alike. A call that carries no person comes from an automation or another integration and is trusted, as Home Assistant trusts it.
