---
domain: import-and-export
availability:
- {place: 'panel::administration'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/appliance_report.py#build_report
---

# Export the appliance report

Save a CSV of every appliance with make, model, replacement cost, the value of spares on hand, its custom fields and a total, for an insurance claim.
