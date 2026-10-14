---
domain: companions
availability:
- {place: 'panel::administration'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/store.py#HomeKeeperStore
- kind: doc
  role: intent
  target: docs/guide/views/settings.md
---

# Edit a declarative companion

Change a declarative companion, including switching it off and on. Its tasks follow: new task labels are added and removed ones taken off, a notes template rewrites the notes, and a switched-off companion stops its tasks until it is on again.
