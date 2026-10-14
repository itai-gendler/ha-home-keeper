---
appliesTo:
- type: capability
  id: create-notification
- type: capability
  id: edit-notification
- type: capability
  id: send-notification
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/notifications.py#split_targets
- kind: doc
  role: intent
  target: docs/SECURITY.md
---

# Notifications go only to companion-app devices and persistent notification

A saved notification keeps only companion-app devices and persistent notification as targets, and a notify call with any other target fails.

## Rationale

Home Keeper never relays text through a channel the caller cannot reach directly, such as an email or chat integration an admin configured.
