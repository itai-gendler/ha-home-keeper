---
domain: companions
availability:
- {place: 'panel::administration'}
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/declarative_companions.py
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/panel-declarative.ts
- kind: doc
  role: intent
  target: docs/guide/views/settings.md
---

# Create a declarative companion

Save a declarative companion, from a preset or blank, that opens a managed task for each entity it matches. The Add companion dialog previews the matches and what each would open; the Tasks tab offers presets that match the home.
