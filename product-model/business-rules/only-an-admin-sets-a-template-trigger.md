---
appliesTo:
- type: entity
  id: task
  effect: creates
  facts:
  - Trigger template
permits:
- actors:
  - admin
  - automation
  - companion
references:
- kind: doc
  role: intent
  target: docs/guide/views/settings.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/__init__.py
---

# Only an admin sets a template trigger on a task

Tasks are open to every signed-in user, except the template trigger: only an admin, an automation or a companion writes one.

## Rationale

A template reads registry data that a user who is not an admin cannot list.
