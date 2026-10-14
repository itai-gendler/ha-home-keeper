---
type: web
actors:
- admin
- household-member
entryPoints:
- web: /home-keeper
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/panel.py
- kind: code
  role: implementation
  target: custom_components/home_keeper/frontend/src/panel.ts
- kind: doc
  role: intent
  target: docs/guide/start/panel.md
---

# Home Keeper panel

The Home Keeper page in the Home Assistant sidebar, with the Tasks, Appliances and Settings tabs.
Every signed-in Home Assistant user opens it; admins also administer appliances and settings there.
