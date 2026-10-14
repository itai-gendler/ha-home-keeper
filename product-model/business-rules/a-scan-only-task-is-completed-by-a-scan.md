---
appliesTo:
- type: entity
  id: completion
  effect: creates
  contexts:
  - {place: 'panel::household'}
  - {place: dashboard-card}
  - {place: native-entities}
  - {place: mobile-notifications}
  - {place: services}
permits:
- unattended: true
- actors:
  - household-member
  - admin
  - automation
  - companion
  when:
  - entity: task
    fact: Require tag scan
    is: 'Off'
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/tags.py#completion_allowed
- kind: doc
  role: intent
  target: docs/guide/tasks/nfc-tags.md
---

# A task that requires a tag scan is completed only by scanning its tag

With Require tag scan on, the panel, the card, the to-do list, the device button, notifications and the complete action refuse Done; scanning the tag completes the task.

## Rationale

The scan is what makes done mean that somebody stood in front of the thing.
