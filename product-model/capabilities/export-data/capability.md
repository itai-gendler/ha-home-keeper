---
domain: import-and-export
availability:
- {place: 'panel::administration'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/transfer_runner.py#async_export
- kind: doc
  role: intent
  target: docs/guide/automation/import-export.md
---

# Export data

Save the tasks and appliances with their history, and the data of companions that support it, as a YAML file, or as a zip bundle that also holds the files and, when checked, the settings.
