---
type: api
actors:
- admin
- household-member
- automation
- companion
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/services.yaml
- kind: code
  role: implementation
  target: custom_components/home_keeper/__init__.py
- kind: doc
  role: intent
  target: docs/guide/automation/services.md
---

# Services

The `home_keeper.*` actions. Automations, scripts, voice and other integrations call them to do
what the panel does; a call from a signed-in person carries that person, and a call with no person
comes from an automation or an integration.
