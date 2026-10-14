---
domain: import-and-export
availability:
- {place: 'panel::administration'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/transfer_runner.py
- kind: code
  role: implementation
  target: custom_components/home_keeper/transfer.py
- kind: doc
  role: intent
  target: docs/guide/automation/import-export.md
---

# Import data

Read a YAML file or a bundle back: preview what would change, then import. Each record updates the one it matches by id, external id or name, or is created; history and skips are added in date order.
