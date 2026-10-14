---
appliesTo:
- type: capability
  id: export-data
- type: capability
  id: import-data
- type: capability
  id: export-appliance-report
references:
- kind: doc
  role: intent
  target: docs/SECURITY.md
---

# Export, import and the appliance report are admin operations

These read or write the whole store, so the panel offers them in Settings and the actions refuse a caller who is not an admin; an automation with no person behind it may call them.
